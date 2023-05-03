Download Link: https://assignmentchef.com/product/solved-cs-208-hw-4b-stochastic-gradient-descent-and-lipschitz-extensions
<br>
<strong>Instructions: </strong>Submit a single PDF file containing your solutions, plots, and analyses. Make sure to thoroughly explain your process and results for each problem. Also include your documented code and a link to a public repository with your code (such as GitHub/GitLab). Make sure to list all collaborators and references.

<ol>

 <li>For each of the following sets G of datasets and neighbor relations ∼, hypotheses H ⊆ G, and functions <em>f </em>: G → R, calculate (i) the global sensitivity of <em>f </em>(denoted GS<em><sub>f </sub></em>or <em>∂f</em>), (ii) the minimum local sensitivity of <em>f</em>, i.e. min<em><sub>x</sub></em><sub>∈</sub><sub>G </sub>LS<em><sub>f</sub></em>(<em>x</em>), and (iii) the restricted sensitivity of <em>f </em>(denoted <em>∂</em><sub>H</sub><em>f </em>or RS<sup>H</sup><em><sub>f </sub></em>). For Part 1a, also describe an explicit Lipschitz extension of <em>f </em>from H to all of G.

  <ul>

   <li>G = R<em><sup>n </sup></em>where <em>x </em>∼ <em>x</em><sup>0 </sup>if <em>x </em>and <em>x</em><sup>0 </sup>differ on one row, H = [<em>a,b</em>]<em><sup>n </sup></em>for real numbers <em>a </em>≤ <em>b</em>, and <em>f</em>(<em>x</em>) = (1<em>/n</em>)<sup>P<em>n</em></sup><em><sub>i</sub></em><sub>=1 </sub><em>x<sub>i</sub></em>.</li>

   <li>G = R<em><sup>n </sup></em>where <em>x </em>∼ <em>x</em><sup>0 </sup>if <em>x </em>and <em>x</em><sup>0 </sup>differ on one row, H = [<em>a,b</em>]<em><sup>n </sup></em>for real numbers <em>a </em>≤ <em>b</em>, and <em>f</em>(<em>x</em>) = median(<em>x</em><sub>1</sub><em>,…,x<sub>n</sub></em>).</li>

   <li>G = the set of undirected graphs (without self-loops) on vertex set {1<em>,…,n</em>} where <em>x </em>∼ <em>x</em><sup>0 </sup>if <em>x </em>and <em>x</em><sup>0 </sup>are identical except for the neighborhood of a single vertex (i.e. node privacy), H = the set of graphs in G in which every vertex has degree at most <em>d </em>for a parameter 2 ≤ <em>d </em>≤ <em>n </em>− 1, and <em>f</em>(<em>x</em>) = the number of isolated (i.e. degree 0) vertices in <em>x</em>.</li>

  </ul></li>

 <li>In our code example,<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> we saw how to release an estimated Logistic regression using differentially private stochastic gradient descent (DP-SGD) to optimize the log-likelihood loss function under the centralized model. Convert this code to once again release the probability of marriage given education level, but using DP-SGD under the <em>local </em><a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> Recall that local DP does not satisfy privacy amplification by subsampling, but you can achieve a similar effect by rotating through disjoint batches, so that each individual partipates in at most d<em>T </em>·<em>B/n</em>e batches, where <em>T </em>is the number of iterations and <em>B </em>is the batch size.<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a> Evaluate the performance of your method as a function of (fixing <em>δ </em>= 1×10<sup>−6</sup>), by showing the classification error over , compared to the RMSE of the coefficients compared to the non-privacy preserving estimates.</li>

</ol>

1

<a href="#_ftnref1" name="_ftn1">[1]</a> See <a href="https://github.com/privacytoolsproject/cs208/blob/master/examples/wk7_localmodel/privateSGD.r">https://github.com/privacytoolsproject/cs208/blob/master/examples/wk7_localmodel/privateSGD. </a><a href="https://github.com/privacytoolsproject/cs208/blob/master/examples/wk7_localmodel/privateSGD.r">r</a> and <a href="https://github.com/privacytoolsproject/cs208/blob/master/examples/wk7_localmodel/privateSGD.ipynb">privateSGD.ipynb</a><a href="https://github.com/privacytoolsproject/cs208/blob/master/examples/wk7_localmodel/privateSGD.ipynb">.</a>

<a href="#_ftnref2" name="_ftn2">[2]</a> For some useful guidance, look at the class notes for April 8th at <a href="http://people.seas.harvard.edu/~salil/cs208/spring19/MLwithDP-lecture.pdf">http://people.seas.harvard.edu/</a><a href="http://people.seas.harvard.edu/~salil/cs208/spring19/MLwithDP-lecture.pdf">~</a><a href="http://people.seas.harvard.edu/~salil/cs208/spring19/MLwithDP-lecture.pdf">salil/</a>

<a href="http://people.seas.harvard.edu/~salil/cs208/spring19/MLwithDP-lecture.pdf">cs208/spring19/MLwithDP-lecture.pdf</a><a href="http://people.seas.harvard.edu/~salil/cs208/spring19/MLwithDP-lecture.pdf">.</a>

<a href="http://people.seas.harvard.edu/~salil/cs208/spring19/MLwithDP-lecture.pdf">√</a>           √

<a href="#_ftnref3" name="_ftn3">[3]</a> 3Note, in the code example, <em>T </em>=               <em>n, B </em>=       <em>n</em>.