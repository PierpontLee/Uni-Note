
# Basic:
![[Pasted image 20260526110044.png]]
![[Pasted image 20260521174933.png]]

$$Var(aX) = a^2 \times Var(X)$$
$$Var(X) = E[X^2] - (E[X])^2$$
$$\ln(ab) = \ln a+\ln b$$
$$\ln(e^k) = k$$

# Chap 1

# Chap 6
==independent identically distributed== (i.i.d.) ==random variables== with mean $\mu$ and variance $\theta^2$
$$\huge E(\bar X^2) = \mu$$
$$\huge Var(\bar X) = \frac{\sigma^2}{\theta}$$
1. Point Estimate:
$$
\hat p = \frac{x}{n}
$$
- x: Number of successes
- n: Number of samples

2. Unbiased estimator:
$$E(\theta\hat) = \theta$$

3. Variance of Uniform distribution:
$$Var(x)=\frac{(b-a)^2}{12}$$

4. Standard Error:
$$\huge\sigma_\hat\theta = \sqrt{var(\hat\theta)}$$
5.  Estimated Standard error:
		Just change: $\huge s_\hat\theta = \hat \sigma_\hat\theta$
6.  Find Moment estimator
	1. Know the distribution
	2. Set $\huge E(X)=\bar X$
	3. Solve for $\lambda\:$ or other
7. Sample Moments
	1. 1st sample moment:
			$$\huge \bar X = \frac{1}{n} \sum xi$$
	2. 2nd sample moment:
			$$\huge \frac{1}{n}\sum X^2_i$$
8. Finding maximum likelihood estimate of _
	1. Find the given function or distribution $\huge L(\_)$ if not given function then add $\huge \prod^N_{i=1}$
	2. $\huge l(\_) = \ln L(\_)$
	3. $\huge l'(\_)$ respect to the "$\huge \_$"
	4. set = 0
	5. check $\huge l''(\_) < 0$
9. MOmenty estimator
	1. E(x) = inmteral x _
	2. Set equal to X \bar