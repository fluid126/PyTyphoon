# PyTyphoon
Python implementation of [Typhoon motion estimator](http://www.pierrederian.net/typhoon.html): dense estimation of 2D optical flow on wavelet bases, primarily aimed at **fluid motion estimation**.

## Important remark
At the moment, the wavelet-based data DFD term [(D&eacute;rian et al., 2013)] only is provided: the **high-order regularizers** [(Kadri-Harouna et al., 2013)] **are not included** in this implementation.

## Requirements
- [Numpy, Scipy](https://scipy.org/);
- [PyWavelets](https://github.com/PyWavelets/pywt);
- [Matplotlib](https://matplotlib.org/) for the demos.

Tested with Anaconda Python 3.6.1, Numpy 1.12.1, Scipy 0.19.1, PyWavelet 0.5.2.

## Todo
- multi-pass estimation (pyramid) for very large displacements;
- 3D extension?;
- some regularizers;
- ...

## Usage
The `Typhoon` class can be imported from other modules/scripts to perform estimations as needed.

The script can also work as a standalone estimator in simple cases, e.g.:
`python pytyphoon.py -i0 path/to/im0.jpg -i1 path/to/im1.jpg -wav 'db3' --display`
will solve the problem for image pair (`im0.jpg`, `im1.jpg`) and wavelet Daubechies-3.
See `python pytyphoon.py -h` for the list of parameters.

## Demos

### Synthetic particle images
Run `python pytyphoon.py --demo particles`.
![Particle results](demo/demo_particles.png)

## References
- [(D&eacute;rian et al., 2013)]
    D&eacute;rian, P.; H&eacute;as, P.; Herzet, C. & M&eacute;min, E.
    "Wavelets and Optical Flow Motion Estimation".
    _Numerical Mathematics: Theory, Method and Applications_, Vol. 6, pp. 116-137, 2013.
- [(Kadri-Harouna et al., 2013)] Kadri Harouna, S.; D&eacute;rian, P.; H&eacute;as, P. and     M&eacute;min, E.
   "Divergence-free Wavelets and High Order Regularization".
   _International Journal of Computer Vision_, Vol. 103, pp. 80-99, 2013.

[(D&eacute;rian et al., 2013)]: https://www.cambridge.org/core/journals/numerical-mathematics-theory-methods-and-applications/article/wavelets-and-optical-flow-motion-estimation/2A9D13B316F000F0530AD42621B42FFD
[(Kadri-Harouna et al., 2013)]: https://link.springer.com/article/10.1007/s11263-012-0595-7
