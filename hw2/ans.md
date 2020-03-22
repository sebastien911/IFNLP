## 1(a)

cross entropy: $-\sum_w y_wlog(\hat{y}_w)$

naive-softmax loss: $-log(\hat{y}_o)$
$$
-\sum_w y_wlog(\hat{y}_w)=-\sum_w \delta(w=o) log(\hat{y}_w)=-log(\hat{y}_o)
$$

## 1(b)

$$
\frac{\partial}{\partial v_c}J=\frac{\partial}{\partial v_c}-log\frac{exp(u_o^Tv_c)}{\sum_{w}exp(u_w^Tv_c)}
$$

$$
=-[\frac{exp(u_o^Tv_c)}{\sum_{w}exp(u_w^Tv_c)}]^{-1}[\frac{exp(u_o^Tv_c)u_o}{\sum_{w}exp(u_w^Tv_c)}-\frac{exp(u_o^Tv_c)\sum_{k}exp(u_k^Tv_c)u_k}{(\sum_{w}exp(u_w^Tv_c))^2}]
$$

$$
=-u_o+\sum_k \frac{exp(u_k^Tv_c)}{\sum_{w}exp(u_w^Tv_c)}u_k
$$

$$
=U^T(\hat{y}-y)
$$

## 1(c)

$$
\frac{\partial}{\partial u_w}J=\frac{\partial}{\partial u_w}-log\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}
$$

$$
=-[\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}]^{-1}\frac{\partial}{\partial u_w}\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}
$$



when $w=o$:
$$
=-[\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}]^{-1}\frac{\partial}{\partial u_o}\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}
$$

$$
=-[\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}]^{-1}[\frac{exp(u_o^Tv_c)v_c}{\sum_{k}exp(u_k^Tv_c)}-\frac{exp(u_o^Tv_c)exp(u_o^Tv_c)v_c}{(\sum_{k}exp(u_k^Tv_c))^2}]
$$

$$
=(\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}-1)v_c
$$



when $w\neq o$:
$$
=-[\frac{exp(u_o^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}]^{-1}[-\frac{exp(u_o^Tv_c)exp(u_k^Tv_c)v_c}{(\sum_{k}exp(u_k^Tv_c))^2}]
$$

$$
=\frac{exp(u_w^Tv_c)}{\sum_{k}exp(u_k^Tv_c)}v_c
$$

summary:
$$
\frac{\partial}{\partial u_w}J=(\hat{y}-y)v_c
$$

## 1(d)

$$
\frac{\partial}{\partial x}\sigma(x)=\frac{\partial}{\partial x}\frac{e^x}{e^x+1}
$$

$$
=\frac{e^x}{e^x+1}-\frac{e^{2x}}{(e^x+1)^2}
$$

$$
=\sigma(x)(1-\sigma(x))
$$

## 1(e)

