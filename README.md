# 14-DBDA

Aoshima and Yata (2014) considered a scale adjusted-type distance-based classifier for high-dimensional data. High-dimensional data situation occur in many areas of modern science, such as genetic mocroarrays, medical imaging, etc. A common feature of high-dimensional data is that the data dimension is high, however, the sample size is relatively small. This is the so-called 'HDLSS'.

Suppose we have independent and p-variate populations, 
<a href="https://www.codecogs.com/eqnedit.php?latex=\pi_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\pi_i" title="\pi_i" /></a>, <a href="https://www.codecogs.com/eqnedit.php?latex=i=1,&space;\ldots,&space;k" target="_blank"><img src="https://latex.codecogs.com/gif.latex?i=1,&space;\ldots,&space;k" title="i=1, \ldots, k" /></a>
, having unknown mean vector
<a href="https://www.codecogs.com/eqnedit.php?latex={\boldsymbol&space;\mu}_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\boldsymbol&space;\mu}_i" title="{\boldsymbol \mu}_i" /></a>
and unknown covariance matrix 
<a href="https://www.codecogs.com/eqnedit.php?latex={\boldsymbol&space;\Sigma}_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\boldsymbol&space;\Sigma}_i" title="{\boldsymbol \Sigma}_i" /></a>
for each 
<a href="https://www.codecogs.com/eqnedit.php?latex=\pi_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\pi_i" title="\pi_i" /></a>. 
We have independent and identically distribution (i.i.d) observations, 
<a href="https://www.codecogs.com/eqnedit.php?latex={\bf&space;x}_{i1},&space;\ldots,{\bf&space;x}_{in_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\bf&space;x}_{i1},&space;\ldots,{\bf&space;x}_{in_i}" title="{\bf x}_{i1}, \ldots,{\bf x}_{in_i}" /></a>, 
from each 
<a href="https://www.codecogs.com/eqnedit.php?latex=\pi_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\pi_i" title="\pi_i" /></a>. 
Let 
<a href="https://www.codecogs.com/eqnedit.php?latex={\bf&space;x}_0" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\bf&space;x}_0" title="{\bf x}_0" /></a>
be an ovservation vector belonging to one of 
<a href="https://www.codecogs.com/eqnedit.php?latex=\pi_i,&space;i=1,&space;\ldots,&space;k" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\pi_i,&space;i=1,&space;\ldots,&space;k" title="\pi_i, i=1, \ldots, k" /></a>. 
We estimate 
<a href="https://www.codecogs.com/eqnedit.php?latex={\boldsymbol&space;\mu}_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\boldsymbol&space;\mu}_i" title="{\boldsymbol \mu}_i" /></a>
and
<a href="https://www.codecogs.com/eqnedit.php?latex={\boldsymbol&space;\Sigma}_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\boldsymbol&space;\Sigma}_i" title="{\boldsymbol \Sigma}_i" /></a>
by
<a href="https://www.codecogs.com/eqnedit.php?latex=\overline{{\bf&space;x}}_{in_i}&space;=&space;{\textstyle&space;\sum_{j=1}^{n_i}&space;{\bf&space;x}_{ij}&space;/&space;n_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\overline{{\bf&space;x}}_{in_i}&space;=&space;{\textstyle&space;\sum_{j=1}^{n_i}&space;{\bf&space;x}_{ij}&space;/&space;n_i}" title="\overline{{\bf x}}_{in_i} = {\textstyle \sum_{j=1}^{n_i} {\bf x}_{ij} / n_i}" /></a>
and
<a href="https://www.codecogs.com/eqnedit.php?latex={\bf&space;S}_{in_i}&space;=&space;{\textstyle&space;\sum_{j=1}^{n_i}&space;({\bf&space;x}_{ij}&space;-&space;\overline{{\bf&space;x}}_{in_i})({\bf&space;x}_{ij}&space;-&space;\overline{{\bf&space;x}}_{in_i})^T&space;/&space;(n_i&space;-&space;1)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\bf&space;S}_{in_i}&space;=&space;{\textstyle&space;\sum_{j=1}^{n_i}&space;({\bf&space;x}_{ij}&space;-&space;\overline{{\bf&space;x}}_{in_i})({\bf&space;x}_{ij}&space;-&space;\overline{{\bf&space;x}}_{in_i})^T&space;/&space;(n_i&space;-&space;1)}" title="{\bf S}_{in_i} = {\textstyle \sum_{j=1}^{n_i} ({\bf x}_{ij} - \overline{{\bf x}}_{in_i})({\bf x}_{ij} - \overline{{\bf x}}_{in_i})^T / (n_i - 1)}" /></a>. 
When
<a href="https://www.codecogs.com/eqnedit.php?latex=k=2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?k=2" title="k=2" /></a>, 
a typecal classification rule is that one classifies an individual into
<a href="https://www.codecogs.com/eqnedit.php?latex=\pi_1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\pi_1" title="\pi_1" /></a>
if 

<a href="https://www.codecogs.com/eqnedit.php?latex=({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{1n_1})^T&space;{\bf&space;S}_{1n_1}^{-1}&space;({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{1n_1})&space;-&space;\log\{\mathrm{det}({\bf&space;S}_{2n_2})&space;/&space;\mathrm{det}({\bf&space;S}_{1n_1})&space;\}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{1n_1})^T&space;{\bf&space;S}_{1n_1}^{-1}&space;({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{1n_1})&space;-&space;\log\{\mathrm{det}({\bf&space;S}_{2n_2})&space;/&space;\mathrm{det}({\bf&space;S}_{1n_1})&space;\}" title="({\bf x}_0 - \overline{{\bf x}}_{1n_1})^T {\bf S}_{1n_1}^{-1} ({\bf x}_0 - \overline{{\bf x}}_{1n_1}) - \log\{\mathrm{det}({\bf S}_{2n_2}) / \mathrm{det}({\bf S}_{1n_1}) \}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=<&space;({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{2n_2})^T&space;{\bf&space;S}_{2n_2}^{-1}&space;({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{2n_2})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?<&space;({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{2n_2})^T&space;{\bf&space;S}_{2n_2}^{-1}&space;({\bf&space;x}_0&space;-&space;\overline{{\bf&space;x}}_{2n_2})" title="< ({\bf x}_0 - \overline{{\bf x}}_{2n_2})^T {\bf S}_{2n_2}^{-1} ({\bf x}_0 - \overline{{\bf x}}_{2n_2})" /></a>,

and into 
<a href="https://www.codecogs.com/eqnedit.php?latex=\pi_2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\pi_2" title="\pi_2" /></a>
otherwise. However, the inverse matrix of 
<a href="https://www.codecogs.com/eqnedit.php?latex={\bf&space;S}_{in_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\bf&space;S}_{in_i}" title="{\bf S}_{in_i}" /></a>
does not exist in HDLSS context.

Aoshima and Yata (2014) considered a new classification rule thet is given by substituting the identity matrix 
<a href="https://www.codecogs.com/eqnedit.php?latex={\bf&space;I}_p" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\bf&space;I}_p" title="{\bf I}_p" /></a>
for 
<a href="https://www.codecogs.com/eqnedit.php?latex={\bf&space;S}_{in_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{\bf&space;S}_{in_i}" title="{\bf S}_{in_i}" /></a>
: one classifies an individual into 
<a href="https://www.codecogs.com/eqnedit.php?latex=\pi_1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\pi_1" title="\pi_1" /></a>
if

<a href="https://www.codecogs.com/eqnedit.php?latex=\left({\bf&space;x}_0&space;-&space;\frac{\overline{{\bf&space;x}}_{1n_1}&space;&plus;&space;\overline{{\bf&space;x}}_{2n_2}}{2}&space;\right)^T&space;\left(&space;\overline{{\bf&space;x}}_{2n_2}&space;-&space;\overline{{\bf&space;x}}_{1n_1}&space;\right)&space;-&space;\frac{\mathrm{tr}\left({\bf&space;S}_{1n_1}\right)}{2n_1}&space;&plus;&space;\frac{\mathrm{tr}\left({\bf&space;S}_{2n_2}\right)}{2n_2}&space;<&space;0" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\left({\bf&space;x}_0&space;-&space;\frac{\overline{{\bf&space;x}}_{1n_1}&space;&plus;&space;\overline{{\bf&space;x}}_{2n_2}}{2}&space;\right)^T&space;\left(&space;\overline{{\bf&space;x}}_{2n_2}&space;-&space;\overline{{\bf&space;x}}_{1n_1}&space;\right)&space;-&space;\frac{\mathrm{tr}\left({\bf&space;S}_{1n_1}\right)}{2n_1}&space;&plus;&space;\frac{\mathrm{tr}\left({\bf&space;S}_{2n_2}\right)}{2n_2}&space;<&space;0" title="\left({\bf x}_0 - \frac{\overline{{\bf x}}_{1n_1} + \overline{{\bf x}}_{2n_2}}{2} \right)^T \left( \overline{{\bf x}}_{2n_2} - \overline{{\bf x}}_{1n_1} \right) - \frac{\mathrm{tr}\left({\bf S}_{1n_1}\right)}{2n_1} + \frac{\mathrm{tr}\left({\bf S}_{2n_2}\right)}{2n_2} < 0" /></a>


