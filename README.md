# xcorr_python
Cross-correlation coefficients in Python

Returns coefficients (or inner product) and lags

This might save someone a bit of time, I could not find a standard xcorr function (like MATLAB's) in Python, which returns the *coefficients* of a cross correlation of two signals (instead of the inner product). 

This code is adapted from [matplotlib's xcorr function](https://matplotlib.org/examples/pylab_examples/xcorr_demo.html "matplotlib xcorr()"), I just separated the normalization from the plotting behavior.

Calls [numpy.correlate(x,y, mode='full')](https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.correlate.html "numpy.correlate()")

#### This is the necessary transformation function (inner product -> coeffs.)
n = np.sqrt(np.dot(x, x) * np.dot(y, y)) 

coeffs = np.true_divide(innerproduct,n)
