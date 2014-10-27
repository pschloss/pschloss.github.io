---
title       : "Reproducibility in microbiome research"
subtitle    : ""
date        : October 27, 2014
author      : Patrick D. Schloss, PhD
job         : The Department of Microbiology & Immunology at The University of Michigan
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      #
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : standalone    # {selfcontained, standalone, draft}
knit        : slidify::knit2slides
--- 

<script type="text/javascript">
CanvasMatrix4=function(m){if(typeof m=='object'){if("length"in m&&m.length>=16){this.load(m[0],m[1],m[2],m[3],m[4],m[5],m[6],m[7],m[8],m[9],m[10],m[11],m[12],m[13],m[14],m[15]);return}else if(m instanceof CanvasMatrix4){this.load(m);return}}this.makeIdentity()};CanvasMatrix4.prototype.load=function(){if(arguments.length==1&&typeof arguments[0]=='object'){var matrix=arguments[0];if("length"in matrix&&matrix.length==16){this.m11=matrix[0];this.m12=matrix[1];this.m13=matrix[2];this.m14=matrix[3];this.m21=matrix[4];this.m22=matrix[5];this.m23=matrix[6];this.m24=matrix[7];this.m31=matrix[8];this.m32=matrix[9];this.m33=matrix[10];this.m34=matrix[11];this.m41=matrix[12];this.m42=matrix[13];this.m43=matrix[14];this.m44=matrix[15];return}if(arguments[0]instanceof CanvasMatrix4){this.m11=matrix.m11;this.m12=matrix.m12;this.m13=matrix.m13;this.m14=matrix.m14;this.m21=matrix.m21;this.m22=matrix.m22;this.m23=matrix.m23;this.m24=matrix.m24;this.m31=matrix.m31;this.m32=matrix.m32;this.m33=matrix.m33;this.m34=matrix.m34;this.m41=matrix.m41;this.m42=matrix.m42;this.m43=matrix.m43;this.m44=matrix.m44;return}}this.makeIdentity()};CanvasMatrix4.prototype.getAsArray=function(){return[this.m11,this.m12,this.m13,this.m14,this.m21,this.m22,this.m23,this.m24,this.m31,this.m32,this.m33,this.m34,this.m41,this.m42,this.m43,this.m44]};CanvasMatrix4.prototype.getAsWebGLFloatArray=function(){return new WebGLFloatArray(this.getAsArray())};CanvasMatrix4.prototype.makeIdentity=function(){this.m11=1;this.m12=0;this.m13=0;this.m14=0;this.m21=0;this.m22=1;this.m23=0;this.m24=0;this.m31=0;this.m32=0;this.m33=1;this.m34=0;this.m41=0;this.m42=0;this.m43=0;this.m44=1};CanvasMatrix4.prototype.transpose=function(){var tmp=this.m12;this.m12=this.m21;this.m21=tmp;tmp=this.m13;this.m13=this.m31;this.m31=tmp;tmp=this.m14;this.m14=this.m41;this.m41=tmp;tmp=this.m23;this.m23=this.m32;this.m32=tmp;tmp=this.m24;this.m24=this.m42;this.m42=tmp;tmp=this.m34;this.m34=this.m43;this.m43=tmp};CanvasMatrix4.prototype.invert=function(){var det=this._determinant4x4();if(Math.abs(det)<1e-8)return null;this._makeAdjoint();this.m11/=det;this.m12/=det;this.m13/=det;this.m14/=det;this.m21/=det;this.m22/=det;this.m23/=det;this.m24/=det;this.m31/=det;this.m32/=det;this.m33/=det;this.m34/=det;this.m41/=det;this.m42/=det;this.m43/=det;this.m44/=det};CanvasMatrix4.prototype.translate=function(x,y,z){if(x==undefined)x=0;if(y==undefined)y=0;if(z==undefined)z=0;var matrix=new CanvasMatrix4();matrix.m41=x;matrix.m42=y;matrix.m43=z;this.multRight(matrix)};CanvasMatrix4.prototype.scale=function(x,y,z){if(x==undefined)x=1;if(z==undefined){if(y==undefined){y=x;z=x}else z=1}else if(y==undefined)y=x;var matrix=new CanvasMatrix4();matrix.m11=x;matrix.m22=y;matrix.m33=z;this.multRight(matrix)};CanvasMatrix4.prototype.rotate=function(angle,x,y,z){angle=angle/180*Math.PI;angle/=2;var sinA=Math.sin(angle);var cosA=Math.cos(angle);var sinA2=sinA*sinA;var length=Math.sqrt(x*x+y*y+z*z);if(length==0){x=0;y=0;z=1}else if(length!=1){x/=length;y/=length;z/=length}var mat=new CanvasMatrix4();if(x==1&&y==0&&z==0){mat.m11=1;mat.m12=0;mat.m13=0;mat.m21=0;mat.m22=1-2*sinA2;mat.m23=2*sinA*cosA;mat.m31=0;mat.m32=-2*sinA*cosA;mat.m33=1-2*sinA2;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}else if(x==0&&y==1&&z==0){mat.m11=1-2*sinA2;mat.m12=0;mat.m13=-2*sinA*cosA;mat.m21=0;mat.m22=1;mat.m23=0;mat.m31=2*sinA*cosA;mat.m32=0;mat.m33=1-2*sinA2;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}else if(x==0&&y==0&&z==1){mat.m11=1-2*sinA2;mat.m12=2*sinA*cosA;mat.m13=0;mat.m21=-2*sinA*cosA;mat.m22=1-2*sinA2;mat.m23=0;mat.m31=0;mat.m32=0;mat.m33=1;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}else{var x2=x*x;var y2=y*y;var z2=z*z;mat.m11=1-2*(y2+z2)*sinA2;mat.m12=2*(x*y*sinA2+z*sinA*cosA);mat.m13=2*(x*z*sinA2-y*sinA*cosA);mat.m21=2*(y*x*sinA2-z*sinA*cosA);mat.m22=1-2*(z2+x2)*sinA2;mat.m23=2*(y*z*sinA2+x*sinA*cosA);mat.m31=2*(z*x*sinA2+y*sinA*cosA);mat.m32=2*(z*y*sinA2-x*sinA*cosA);mat.m33=1-2*(x2+y2)*sinA2;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}this.multRight(mat)};CanvasMatrix4.prototype.multRight=function(mat){var m11=(this.m11*mat.m11+this.m12*mat.m21+this.m13*mat.m31+this.m14*mat.m41);var m12=(this.m11*mat.m12+this.m12*mat.m22+this.m13*mat.m32+this.m14*mat.m42);var m13=(this.m11*mat.m13+this.m12*mat.m23+this.m13*mat.m33+this.m14*mat.m43);var m14=(this.m11*mat.m14+this.m12*mat.m24+this.m13*mat.m34+this.m14*mat.m44);var m21=(this.m21*mat.m11+this.m22*mat.m21+this.m23*mat.m31+this.m24*mat.m41);var m22=(this.m21*mat.m12+this.m22*mat.m22+this.m23*mat.m32+this.m24*mat.m42);var m23=(this.m21*mat.m13+this.m22*mat.m23+this.m23*mat.m33+this.m24*mat.m43);var m24=(this.m21*mat.m14+this.m22*mat.m24+this.m23*mat.m34+this.m24*mat.m44);var m31=(this.m31*mat.m11+this.m32*mat.m21+this.m33*mat.m31+this.m34*mat.m41);var m32=(this.m31*mat.m12+this.m32*mat.m22+this.m33*mat.m32+this.m34*mat.m42);var m33=(this.m31*mat.m13+this.m32*mat.m23+this.m33*mat.m33+this.m34*mat.m43);var m34=(this.m31*mat.m14+this.m32*mat.m24+this.m33*mat.m34+this.m34*mat.m44);var m41=(this.m41*mat.m11+this.m42*mat.m21+this.m43*mat.m31+this.m44*mat.m41);var m42=(this.m41*mat.m12+this.m42*mat.m22+this.m43*mat.m32+this.m44*mat.m42);var m43=(this.m41*mat.m13+this.m42*mat.m23+this.m43*mat.m33+this.m44*mat.m43);var m44=(this.m41*mat.m14+this.m42*mat.m24+this.m43*mat.m34+this.m44*mat.m44);this.m11=m11;this.m12=m12;this.m13=m13;this.m14=m14;this.m21=m21;this.m22=m22;this.m23=m23;this.m24=m24;this.m31=m31;this.m32=m32;this.m33=m33;this.m34=m34;this.m41=m41;this.m42=m42;this.m43=m43;this.m44=m44};CanvasMatrix4.prototype.multLeft=function(mat){var m11=(mat.m11*this.m11+mat.m12*this.m21+mat.m13*this.m31+mat.m14*this.m41);var m12=(mat.m11*this.m12+mat.m12*this.m22+mat.m13*this.m32+mat.m14*this.m42);var m13=(mat.m11*this.m13+mat.m12*this.m23+mat.m13*this.m33+mat.m14*this.m43);var m14=(mat.m11*this.m14+mat.m12*this.m24+mat.m13*this.m34+mat.m14*this.m44);var m21=(mat.m21*this.m11+mat.m22*this.m21+mat.m23*this.m31+mat.m24*this.m41);var m22=(mat.m21*this.m12+mat.m22*this.m22+mat.m23*this.m32+mat.m24*this.m42);var m23=(mat.m21*this.m13+mat.m22*this.m23+mat.m23*this.m33+mat.m24*this.m43);var m24=(mat.m21*this.m14+mat.m22*this.m24+mat.m23*this.m34+mat.m24*this.m44);var m31=(mat.m31*this.m11+mat.m32*this.m21+mat.m33*this.m31+mat.m34*this.m41);var m32=(mat.m31*this.m12+mat.m32*this.m22+mat.m33*this.m32+mat.m34*this.m42);var m33=(mat.m31*this.m13+mat.m32*this.m23+mat.m33*this.m33+mat.m34*this.m43);var m34=(mat.m31*this.m14+mat.m32*this.m24+mat.m33*this.m34+mat.m34*this.m44);var m41=(mat.m41*this.m11+mat.m42*this.m21+mat.m43*this.m31+mat.m44*this.m41);var m42=(mat.m41*this.m12+mat.m42*this.m22+mat.m43*this.m32+mat.m44*this.m42);var m43=(mat.m41*this.m13+mat.m42*this.m23+mat.m43*this.m33+mat.m44*this.m43);var m44=(mat.m41*this.m14+mat.m42*this.m24+mat.m43*this.m34+mat.m44*this.m44);this.m11=m11;this.m12=m12;this.m13=m13;this.m14=m14;this.m21=m21;this.m22=m22;this.m23=m23;this.m24=m24;this.m31=m31;this.m32=m32;this.m33=m33;this.m34=m34;this.m41=m41;this.m42=m42;this.m43=m43;this.m44=m44};CanvasMatrix4.prototype.ortho=function(left,right,bottom,top,near,far){var tx=(left+right)/(left-right);var ty=(top+bottom)/(top-bottom);var tz=(far+near)/(far-near);var matrix=new CanvasMatrix4();matrix.m11=2/(left-right);matrix.m12=0;matrix.m13=0;matrix.m14=0;matrix.m21=0;matrix.m22=2/(top-bottom);matrix.m23=0;matrix.m24=0;matrix.m31=0;matrix.m32=0;matrix.m33=-2/(far-near);matrix.m34=0;matrix.m41=tx;matrix.m42=ty;matrix.m43=tz;matrix.m44=1;this.multRight(matrix)};CanvasMatrix4.prototype.frustum=function(left,right,bottom,top,near,far){var matrix=new CanvasMatrix4();var A=(right+left)/(right-left);var B=(top+bottom)/(top-bottom);var C=-(far+near)/(far-near);var D=-(2*far*near)/(far-near);matrix.m11=(2*near)/(right-left);matrix.m12=0;matrix.m13=0;matrix.m14=0;matrix.m21=0;matrix.m22=2*near/(top-bottom);matrix.m23=0;matrix.m24=0;matrix.m31=A;matrix.m32=B;matrix.m33=C;matrix.m34=-1;matrix.m41=0;matrix.m42=0;matrix.m43=D;matrix.m44=0;this.multRight(matrix)};CanvasMatrix4.prototype.perspective=function(fovy,aspect,zNear,zFar){var top=Math.tan(fovy*Math.PI/360)*zNear;var bottom=-top;var left=aspect*bottom;var right=aspect*top;this.frustum(left,right,bottom,top,zNear,zFar)};CanvasMatrix4.prototype.lookat=function(eyex,eyey,eyez,centerx,centery,centerz,upx,upy,upz){var matrix=new CanvasMatrix4();var zx=eyex-centerx;var zy=eyey-centery;var zz=eyez-centerz;var mag=Math.sqrt(zx*zx+zy*zy+zz*zz);if(mag){zx/=mag;zy/=mag;zz/=mag}var yx=upx;var yy=upy;var yz=upz;xx=yy*zz-yz*zy;xy=-yx*zz+yz*zx;xz=yx*zy-yy*zx;yx=zy*xz-zz*xy;yy=-zx*xz+zz*xx;yx=zx*xy-zy*xx;mag=Math.sqrt(xx*xx+xy*xy+xz*xz);if(mag){xx/=mag;xy/=mag;xz/=mag}mag=Math.sqrt(yx*yx+yy*yy+yz*yz);if(mag){yx/=mag;yy/=mag;yz/=mag}matrix.m11=xx;matrix.m12=xy;matrix.m13=xz;matrix.m14=0;matrix.m21=yx;matrix.m22=yy;matrix.m23=yz;matrix.m24=0;matrix.m31=zx;matrix.m32=zy;matrix.m33=zz;matrix.m34=0;matrix.m41=0;matrix.m42=0;matrix.m43=0;matrix.m44=1;matrix.translate(-eyex,-eyey,-eyez);this.multRight(matrix)};CanvasMatrix4.prototype._determinant2x2=function(a,b,c,d){return a*d-b*c};CanvasMatrix4.prototype._determinant3x3=function(a1,a2,a3,b1,b2,b3,c1,c2,c3){return a1*this._determinant2x2(b2,b3,c2,c3)-b1*this._determinant2x2(a2,a3,c2,c3)+c1*this._determinant2x2(a2,a3,b2,b3)};CanvasMatrix4.prototype._determinant4x4=function(){var a1=this.m11;var b1=this.m12;var c1=this.m13;var d1=this.m14;var a2=this.m21;var b2=this.m22;var c2=this.m23;var d2=this.m24;var a3=this.m31;var b3=this.m32;var c3=this.m33;var d3=this.m34;var a4=this.m41;var b4=this.m42;var c4=this.m43;var d4=this.m44;return a1*this._determinant3x3(b2,b3,b4,c2,c3,c4,d2,d3,d4)-b1*this._determinant3x3(a2,a3,a4,c2,c3,c4,d2,d3,d4)+c1*this._determinant3x3(a2,a3,a4,b2,b3,b4,d2,d3,d4)-d1*this._determinant3x3(a2,a3,a4,b2,b3,b4,c2,c3,c4)};CanvasMatrix4.prototype._makeAdjoint=function(){var a1=this.m11;var b1=this.m12;var c1=this.m13;var d1=this.m14;var a2=this.m21;var b2=this.m22;var c2=this.m23;var d2=this.m24;var a3=this.m31;var b3=this.m32;var c3=this.m33;var d3=this.m34;var a4=this.m41;var b4=this.m42;var c4=this.m43;var d4=this.m44;this.m11=this._determinant3x3(b2,b3,b4,c2,c3,c4,d2,d3,d4);this.m21=-this._determinant3x3(a2,a3,a4,c2,c3,c4,d2,d3,d4);this.m31=this._determinant3x3(a2,a3,a4,b2,b3,b4,d2,d3,d4);this.m41=-this._determinant3x3(a2,a3,a4,b2,b3,b4,c2,c3,c4);this.m12=-this._determinant3x3(b1,b3,b4,c1,c3,c4,d1,d3,d4);this.m22=this._determinant3x3(a1,a3,a4,c1,c3,c4,d1,d3,d4);this.m32=-this._determinant3x3(a1,a3,a4,b1,b3,b4,d1,d3,d4);this.m42=this._determinant3x3(a1,a3,a4,b1,b3,b4,c1,c3,c4);this.m13=this._determinant3x3(b1,b2,b4,c1,c2,c4,d1,d2,d4);this.m23=-this._determinant3x3(a1,a2,a4,c1,c2,c4,d1,d2,d4);this.m33=this._determinant3x3(a1,a2,a4,b1,b2,b4,d1,d2,d4);this.m43=-this._determinant3x3(a1,a2,a4,b1,b2,b4,c1,c2,c4);this.m14=-this._determinant3x3(b1,b2,b3,c1,c2,c3,d1,d2,d3);this.m24=this._determinant3x3(a1,a2,a3,c1,c2,c3,d1,d2,d3);this.m34=-this._determinant3x3(a1,a2,a3,b1,b2,b3,d1,d2,d3);this.m44=this._determinant3x3(a1,a2,a3,b1,b2,b3,c1,c2,c3)}
</script>


--- .segue .dark 

### Have you ever wondered why so many cook books suck?

---

## [Elements of the scientific method (according to wikipedia)](http://en.wikipedia.org/wiki/Scientific_method#Elements_of_the_scientific_method)
* Characterizations
* Hypothesis development
* Predictions from the hypothesis
* Experiments
* Evaluation and improvement
* Confirmation

---

## Evaluation and improvement
> * PIs take it on faith that your analysis is right  
> * Few (any?) reviewers actually try to redo your science on any level  
> * Reproducibility is a critical component to doing science  
> * A flawed experiment can screw over a bunch of downstream studies  

---

## Many levels of reproducibility
> * Repeat the general experiment with a different population  
> * Repeat the general experiment with the same population  
> * Repeat the analysis using the same data  
> * Repeat the analysis using the same data and methods  

---

## For a microbiome study, I should be able to read your paper and...  

1. Download your raw, unprocessed data   
2. Read your paper and any supplements to understand what exactly you did to curate the data  
3. Repeat your analysis  
4. Support your results  
5. Do something creative that builds upon what you've done  

---

## Notes

> * This is not about whether ***you*** ....
  * ... did the analysis correctly
  * ... got the "right" answer
> * It is about whether ***I***...
  * ... am able to see what you did and repeat it
  * ... can use your data to do something more
> * Most importantly, this is not about fraud

---

## General trend: Drug discovery

<img src="http://www.nature.com/nrd/journal/v10/n9/images/nrd3439-c1-f1.jpg" style="margin:0px auto;display:block" width="800">

# Bayer HealthCare
# Prinz et al. 2011. Believe it or not: how much can we rely on published data on potential drug targets? Nature Reviews Drug Discovery 10:712 (http://www.nature.com/nrd/journal/v10/n9/full/nrd3439-c1.html)

---

## General trend: Drug discovery

* Researchers from Amgen replicated 53 "landmark" papers and could only confirm 6 (11%) of the findings  
  - C. Glenn Begley	& Lee M. Ellis. 2012. Drug development: Raise standards for preclinical cancer research. Nature. 483:531.

* "An unspoken rule among early-stage venture capital firms that “at least 50% of published studies, even those in top-tier academic journals, can't be repeated with the same conclusions by an industrial lab” has been recently reported (see Further information) and discussed"
  - Prinz et al. 

---

## General trend: Psychology

* [Reproducibility Project](https://osf.io/ezcuj/wiki/home/)
* Some journals are encouraging authors to submit papers attempting to replicate studies
  * Journal of Experimental Psychology: General
  * Journal of Personality and Social Psychology
  * Psychology of Aesthetics, Creativity, and the Arts
* Controversial

---

## Collins/Tabak: Causes of problem (quotes)

* ***Increased emphasis on making provocative statements rather than presenting technical details***
* Poor training of researchers in experimental design
* Publications that do not report basic elements of experimental design
* Few venues for researchers to publish negative data or papers that point out scientific flaws in previously published work.
* Difficulty of accessing unpublished data — and the failure of funding agencies to establish or enforce policies that insist on data access.

---

## Collins/Tabak: Solutions to the problem (quotes)

* NIH is developing a training module on enhancing reproducibility and transparency of research findings, with an emphasis on good experimental design.
* Several of the NIH's institutes and centres are also testing the use of a checklist to ensure a more systematic evaluation of grant applications.
* Perhaps the most vexed issue is the academic incentive system. It currently over-emphasizes publishing in high-profile journals  

> * Meh.

--- &vcenter

<img src="assets/img/DataReproducibilityRFA.png" style="margin:0px auto;display:block" width="1000">

---

## Wommack/Ravel: Does our field have a problem?

* We feel the time is right for the community to set standards for complete transparency and full reproducibility
* Simply providing scripts and workflow is not enough; data and code have to be understandable to be reproducible
* It is no mistake that the best documented tools often turn out to be more frequently used by microbiome researchers

--- &vcenter

<img src="assets/img/HadzaTitle.png" style="margin:0px auto;display:block" width="1000">

---

## I want to replicate this study...

* Validation
  * Spirochetes in the gut(!)
  * Differences between Hadza and Europeans
  * Jeff Leach study
* Ask further questions
  * Are Hadza more similar to US population than to Europeans?
  * Are the Hadza gut spirochaetes the same as their oral spirochaetes?

---

## Possible hurdles: Where to get the data?

* In 15 min we figured out...
  * Not in SRA
  * Some data in MG-RAST, but not all
  * Limited to no metadata
  * Email to PI got very tense response
* The SRA is a pain in the ass and would solve some of these problems

---

## Possible hurdles: How were the data analyzed?

* Limited methods description:  
  - "Sequencing reads were analysed using the QIIME pipeline as described previously"  
  - "Analysis of 454 Pyrosequencing data was done using mothur (version 1.25.1). Briefly, instructions from standard operating procedure (SOP) at the website were followed to process Pyrosequencing data."

* We don't have a culture of adequately documenting our analytical methods
* Over use of GUI and web-driven tools

---

## After a lot of work...

> * Could we replicate their analysis?
>   * No.
> * Why?
>   * No idea.

---

## Now what?

* Contact PI, see what we missed
* Note that we didn't even try to do the analysis ***correctly***!

---

## Is this an isolated incident?
* How accessible are the raw data?
* Is reproducibility dependent on the person trying to reproduce the effort?

---

## What should the goal be?
* Not this!
  * Should ***not*** have to contact the original scientists for help (what happens in 5 years?)
  * Should ***not*** have to distrust original scientists
* `write.paper`
* Note...
  * Anytime you edit a file, you lose reproducibility
  * Anytime you make a decision that is not documented, you lose reproducibility

---

## Literate programming...

* "I believe that the time is ripe for significantly better documentation of programs, and that we can best achieve this by considering programs to be works of literature. Hence, my title: 'Literate Programming.' - Donald Knuth, 1992
* The concept of combining code with documentation

> * `write.paper`

---

## Reproducibile research toolbox 

* Literate programming tools
  - Wikis
  - IPython notebook
  - `knitr` and `slidify` R packages
* Version control: github
* `make`

--- &twocol

## IPython Notebook

*** {name: left}
* An executable wiki
* Can run any programming language (including mothur)
* Can output to any format
* Used for [Ding and Schloss (2014) Nature paper](http://nbviewer.ipython.org/gist/pschloss/9815766/notebook.ipynb)


*** {name: right}
<img src="assets/img/IPythonNotebook.png" style="margin:0px auto;display:block" width="500">

---

## knitr R package

* Very similar to IPython
* Bonus of being able to present varaiables within the text:


```r
random.numbers <- runif(10)
total <- sum(random.numbers)
```

* I randomly drew 10 random numbers. These included: 0.2016555, 0.4256542, 0.4281177, 0.8116443, 0.6468423, 0.6532065, 0.4207476, 0.3120167, 0.0801625, 0.0044682
* Their sum was 3.9845155

---

## slidify R package

<img src="assets/fig/3dplot-1.png" title="plot of chunk 3dplot" alt="plot of chunk 3dplot" style="display: block; margin: auto;" />

--- &twocol

## `write.paper`

*** {name: left}
* Can write a paper in knitr using a combination of `markdown`, `bash`, `R`, `Python`, whatever.
* People have written entire books (what do you think their errata look like?)
* We used this in a paper recently accepted to AEM. 
* Pulls all files from SRA and produces Results section of the paper


*** {name: right}
<img src="assets/img/knitrNotebook.png" style="margin:0px auto;display:block" width="500">

--- &twocol

## Git/GitHub: Version control software (VCS)

*** {name: left}
* A "time machine" of versions of text and software
* Facilitates collaboration
 * In a collaborative setting you can see who changed what
 * Allows for simultaneous editing

*** {name: right}
  <img src="assets/img/phd101212s.gif" alt="Piled Higher and Deeper by Jorge Cham, http://www.phdcomics.com", style="margin:0px auto;display:block" width="400">

---

## Git/GitHub: Version control software (VCS)
* Academic users can have free, private repositories
* Anyone you give permissions to can access the repository, enabling them to...
  * Review your code
  * Copy your code
  * Make suggestions to your code
* When you are ready to publish you can make the repository public
* This talk is on GitHub!

---

## Case study: Leslie et al.

* https://rawgit.com/swhitefi/project1/master/README.html

---



## Let's do an experiment...
* Select N papers from various journals
  * How accessibile are the data?
  * What type of methods description is provided?
* For a subset of those papers
  * If 3 people were selected to replicate the analysis would they all get the original results?
  * If a standard pipeline were used would you get the original results?

---

## Preliminary data from AEM
* 5051 papers from volumes 76-80 (through issue 22)
* 393 papers that looked like they could be 16S/18S rRNA surveys using NGS technologies
* XXX papers confirmed to be 16S/18S rRNA surveys using NGS technologies

---

## Data available?
* XXX in SRA
* XXX in MG-RAST
* XXX in ENA
* XXX on private servers

---

## Methods available
* XXX with minimal description
* XXX with exact commands
* XXX with digital notebooks

---

## What do other journals look like?

* ISMEJ
* PLOS One
* Environmental Microbiology
* Nature Communications
* Nature
* Science



