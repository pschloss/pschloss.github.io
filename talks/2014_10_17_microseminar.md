---
title       : "What is past is prologue: Deciphering assembly rules within the murine microbiome"
subtitle    : "http://goo.gl/VpSm5u"
date        : October 16, 2014
author      : Patrick D. Schloss, PhD (@PatSchloss)
job         : The Department of Microbiology & Immunology at The University of Michigan
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      #
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : standalone    # {selfcontained, standalone, draft}
knit        : slidify::knit2slides
--- .segue .dark

<script type="text/javascript">
CanvasMatrix4=function(m){if(typeof m=='object'){if("length"in m&&m.length>=16){this.load(m[0],m[1],m[2],m[3],m[4],m[5],m[6],m[7],m[8],m[9],m[10],m[11],m[12],m[13],m[14],m[15]);return}else if(m instanceof CanvasMatrix4){this.load(m);return}}this.makeIdentity()};CanvasMatrix4.prototype.load=function(){if(arguments.length==1&&typeof arguments[0]=='object'){var matrix=arguments[0];if("length"in matrix&&matrix.length==16){this.m11=matrix[0];this.m12=matrix[1];this.m13=matrix[2];this.m14=matrix[3];this.m21=matrix[4];this.m22=matrix[5];this.m23=matrix[6];this.m24=matrix[7];this.m31=matrix[8];this.m32=matrix[9];this.m33=matrix[10];this.m34=matrix[11];this.m41=matrix[12];this.m42=matrix[13];this.m43=matrix[14];this.m44=matrix[15];return}if(arguments[0]instanceof CanvasMatrix4){this.m11=matrix.m11;this.m12=matrix.m12;this.m13=matrix.m13;this.m14=matrix.m14;this.m21=matrix.m21;this.m22=matrix.m22;this.m23=matrix.m23;this.m24=matrix.m24;this.m31=matrix.m31;this.m32=matrix.m32;this.m33=matrix.m33;this.m34=matrix.m34;this.m41=matrix.m41;this.m42=matrix.m42;this.m43=matrix.m43;this.m44=matrix.m44;return}}this.makeIdentity()};CanvasMatrix4.prototype.getAsArray=function(){return[this.m11,this.m12,this.m13,this.m14,this.m21,this.m22,this.m23,this.m24,this.m31,this.m32,this.m33,this.m34,this.m41,this.m42,this.m43,this.m44]};CanvasMatrix4.prototype.getAsWebGLFloatArray=function(){return new WebGLFloatArray(this.getAsArray())};CanvasMatrix4.prototype.makeIdentity=function(){this.m11=1;this.m12=0;this.m13=0;this.m14=0;this.m21=0;this.m22=1;this.m23=0;this.m24=0;this.m31=0;this.m32=0;this.m33=1;this.m34=0;this.m41=0;this.m42=0;this.m43=0;this.m44=1};CanvasMatrix4.prototype.transpose=function(){var tmp=this.m12;this.m12=this.m21;this.m21=tmp;tmp=this.m13;this.m13=this.m31;this.m31=tmp;tmp=this.m14;this.m14=this.m41;this.m41=tmp;tmp=this.m23;this.m23=this.m32;this.m32=tmp;tmp=this.m24;this.m24=this.m42;this.m42=tmp;tmp=this.m34;this.m34=this.m43;this.m43=tmp};CanvasMatrix4.prototype.invert=function(){var det=this._determinant4x4();if(Math.abs(det)<1e-8)return null;this._makeAdjoint();this.m11/=det;this.m12/=det;this.m13/=det;this.m14/=det;this.m21/=det;this.m22/=det;this.m23/=det;this.m24/=det;this.m31/=det;this.m32/=det;this.m33/=det;this.m34/=det;this.m41/=det;this.m42/=det;this.m43/=det;this.m44/=det};CanvasMatrix4.prototype.translate=function(x,y,z){if(x==undefined)x=0;if(y==undefined)y=0;if(z==undefined)z=0;var matrix=new CanvasMatrix4();matrix.m41=x;matrix.m42=y;matrix.m43=z;this.multRight(matrix)};CanvasMatrix4.prototype.scale=function(x,y,z){if(x==undefined)x=1;if(z==undefined){if(y==undefined){y=x;z=x}else z=1}else if(y==undefined)y=x;var matrix=new CanvasMatrix4();matrix.m11=x;matrix.m22=y;matrix.m33=z;this.multRight(matrix)};CanvasMatrix4.prototype.rotate=function(angle,x,y,z){angle=angle/180*Math.PI;angle/=2;var sinA=Math.sin(angle);var cosA=Math.cos(angle);var sinA2=sinA*sinA;var length=Math.sqrt(x*x+y*y+z*z);if(length==0){x=0;y=0;z=1}else if(length!=1){x/=length;y/=length;z/=length}var mat=new CanvasMatrix4();if(x==1&&y==0&&z==0){mat.m11=1;mat.m12=0;mat.m13=0;mat.m21=0;mat.m22=1-2*sinA2;mat.m23=2*sinA*cosA;mat.m31=0;mat.m32=-2*sinA*cosA;mat.m33=1-2*sinA2;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}else if(x==0&&y==1&&z==0){mat.m11=1-2*sinA2;mat.m12=0;mat.m13=-2*sinA*cosA;mat.m21=0;mat.m22=1;mat.m23=0;mat.m31=2*sinA*cosA;mat.m32=0;mat.m33=1-2*sinA2;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}else if(x==0&&y==0&&z==1){mat.m11=1-2*sinA2;mat.m12=2*sinA*cosA;mat.m13=0;mat.m21=-2*sinA*cosA;mat.m22=1-2*sinA2;mat.m23=0;mat.m31=0;mat.m32=0;mat.m33=1;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}else{var x2=x*x;var y2=y*y;var z2=z*z;mat.m11=1-2*(y2+z2)*sinA2;mat.m12=2*(x*y*sinA2+z*sinA*cosA);mat.m13=2*(x*z*sinA2-y*sinA*cosA);mat.m21=2*(y*x*sinA2-z*sinA*cosA);mat.m22=1-2*(z2+x2)*sinA2;mat.m23=2*(y*z*sinA2+x*sinA*cosA);mat.m31=2*(z*x*sinA2+y*sinA*cosA);mat.m32=2*(z*y*sinA2-x*sinA*cosA);mat.m33=1-2*(x2+y2)*sinA2;mat.m14=mat.m24=mat.m34=0;mat.m41=mat.m42=mat.m43=0;mat.m44=1}this.multRight(mat)};CanvasMatrix4.prototype.multRight=function(mat){var m11=(this.m11*mat.m11+this.m12*mat.m21+this.m13*mat.m31+this.m14*mat.m41);var m12=(this.m11*mat.m12+this.m12*mat.m22+this.m13*mat.m32+this.m14*mat.m42);var m13=(this.m11*mat.m13+this.m12*mat.m23+this.m13*mat.m33+this.m14*mat.m43);var m14=(this.m11*mat.m14+this.m12*mat.m24+this.m13*mat.m34+this.m14*mat.m44);var m21=(this.m21*mat.m11+this.m22*mat.m21+this.m23*mat.m31+this.m24*mat.m41);var m22=(this.m21*mat.m12+this.m22*mat.m22+this.m23*mat.m32+this.m24*mat.m42);var m23=(this.m21*mat.m13+this.m22*mat.m23+this.m23*mat.m33+this.m24*mat.m43);var m24=(this.m21*mat.m14+this.m22*mat.m24+this.m23*mat.m34+this.m24*mat.m44);var m31=(this.m31*mat.m11+this.m32*mat.m21+this.m33*mat.m31+this.m34*mat.m41);var m32=(this.m31*mat.m12+this.m32*mat.m22+this.m33*mat.m32+this.m34*mat.m42);var m33=(this.m31*mat.m13+this.m32*mat.m23+this.m33*mat.m33+this.m34*mat.m43);var m34=(this.m31*mat.m14+this.m32*mat.m24+this.m33*mat.m34+this.m34*mat.m44);var m41=(this.m41*mat.m11+this.m42*mat.m21+this.m43*mat.m31+this.m44*mat.m41);var m42=(this.m41*mat.m12+this.m42*mat.m22+this.m43*mat.m32+this.m44*mat.m42);var m43=(this.m41*mat.m13+this.m42*mat.m23+this.m43*mat.m33+this.m44*mat.m43);var m44=(this.m41*mat.m14+this.m42*mat.m24+this.m43*mat.m34+this.m44*mat.m44);this.m11=m11;this.m12=m12;this.m13=m13;this.m14=m14;this.m21=m21;this.m22=m22;this.m23=m23;this.m24=m24;this.m31=m31;this.m32=m32;this.m33=m33;this.m34=m34;this.m41=m41;this.m42=m42;this.m43=m43;this.m44=m44};CanvasMatrix4.prototype.multLeft=function(mat){var m11=(mat.m11*this.m11+mat.m12*this.m21+mat.m13*this.m31+mat.m14*this.m41);var m12=(mat.m11*this.m12+mat.m12*this.m22+mat.m13*this.m32+mat.m14*this.m42);var m13=(mat.m11*this.m13+mat.m12*this.m23+mat.m13*this.m33+mat.m14*this.m43);var m14=(mat.m11*this.m14+mat.m12*this.m24+mat.m13*this.m34+mat.m14*this.m44);var m21=(mat.m21*this.m11+mat.m22*this.m21+mat.m23*this.m31+mat.m24*this.m41);var m22=(mat.m21*this.m12+mat.m22*this.m22+mat.m23*this.m32+mat.m24*this.m42);var m23=(mat.m21*this.m13+mat.m22*this.m23+mat.m23*this.m33+mat.m24*this.m43);var m24=(mat.m21*this.m14+mat.m22*this.m24+mat.m23*this.m34+mat.m24*this.m44);var m31=(mat.m31*this.m11+mat.m32*this.m21+mat.m33*this.m31+mat.m34*this.m41);var m32=(mat.m31*this.m12+mat.m32*this.m22+mat.m33*this.m32+mat.m34*this.m42);var m33=(mat.m31*this.m13+mat.m32*this.m23+mat.m33*this.m33+mat.m34*this.m43);var m34=(mat.m31*this.m14+mat.m32*this.m24+mat.m33*this.m34+mat.m34*this.m44);var m41=(mat.m41*this.m11+mat.m42*this.m21+mat.m43*this.m31+mat.m44*this.m41);var m42=(mat.m41*this.m12+mat.m42*this.m22+mat.m43*this.m32+mat.m44*this.m42);var m43=(mat.m41*this.m13+mat.m42*this.m23+mat.m43*this.m33+mat.m44*this.m43);var m44=(mat.m41*this.m14+mat.m42*this.m24+mat.m43*this.m34+mat.m44*this.m44);this.m11=m11;this.m12=m12;this.m13=m13;this.m14=m14;this.m21=m21;this.m22=m22;this.m23=m23;this.m24=m24;this.m31=m31;this.m32=m32;this.m33=m33;this.m34=m34;this.m41=m41;this.m42=m42;this.m43=m43;this.m44=m44};CanvasMatrix4.prototype.ortho=function(left,right,bottom,top,near,far){var tx=(left+right)/(left-right);var ty=(top+bottom)/(top-bottom);var tz=(far+near)/(far-near);var matrix=new CanvasMatrix4();matrix.m11=2/(left-right);matrix.m12=0;matrix.m13=0;matrix.m14=0;matrix.m21=0;matrix.m22=2/(top-bottom);matrix.m23=0;matrix.m24=0;matrix.m31=0;matrix.m32=0;matrix.m33=-2/(far-near);matrix.m34=0;matrix.m41=tx;matrix.m42=ty;matrix.m43=tz;matrix.m44=1;this.multRight(matrix)};CanvasMatrix4.prototype.frustum=function(left,right,bottom,top,near,far){var matrix=new CanvasMatrix4();var A=(right+left)/(right-left);var B=(top+bottom)/(top-bottom);var C=-(far+near)/(far-near);var D=-(2*far*near)/(far-near);matrix.m11=(2*near)/(right-left);matrix.m12=0;matrix.m13=0;matrix.m14=0;matrix.m21=0;matrix.m22=2*near/(top-bottom);matrix.m23=0;matrix.m24=0;matrix.m31=A;matrix.m32=B;matrix.m33=C;matrix.m34=-1;matrix.m41=0;matrix.m42=0;matrix.m43=D;matrix.m44=0;this.multRight(matrix)};CanvasMatrix4.prototype.perspective=function(fovy,aspect,zNear,zFar){var top=Math.tan(fovy*Math.PI/360)*zNear;var bottom=-top;var left=aspect*bottom;var right=aspect*top;this.frustum(left,right,bottom,top,zNear,zFar)};CanvasMatrix4.prototype.lookat=function(eyex,eyey,eyez,centerx,centery,centerz,upx,upy,upz){var matrix=new CanvasMatrix4();var zx=eyex-centerx;var zy=eyey-centery;var zz=eyez-centerz;var mag=Math.sqrt(zx*zx+zy*zy+zz*zz);if(mag){zx/=mag;zy/=mag;zz/=mag}var yx=upx;var yy=upy;var yz=upz;xx=yy*zz-yz*zy;xy=-yx*zz+yz*zx;xz=yx*zy-yy*zx;yx=zy*xz-zz*xy;yy=-zx*xz+zz*xx;yx=zx*xy-zy*xx;mag=Math.sqrt(xx*xx+xy*xy+xz*xz);if(mag){xx/=mag;xy/=mag;xz/=mag}mag=Math.sqrt(yx*yx+yy*yy+yz*yz);if(mag){yx/=mag;yy/=mag;yz/=mag}matrix.m11=xx;matrix.m12=xy;matrix.m13=xz;matrix.m14=0;matrix.m21=yx;matrix.m22=yy;matrix.m23=yz;matrix.m24=0;matrix.m31=zx;matrix.m32=zy;matrix.m33=zz;matrix.m34=0;matrix.m41=0;matrix.m42=0;matrix.m43=0;matrix.m44=1;matrix.translate(-eyex,-eyey,-eyez);this.multRight(matrix)};CanvasMatrix4.prototype._determinant2x2=function(a,b,c,d){return a*d-b*c};CanvasMatrix4.prototype._determinant3x3=function(a1,a2,a3,b1,b2,b3,c1,c2,c3){return a1*this._determinant2x2(b2,b3,c2,c3)-b1*this._determinant2x2(a2,a3,c2,c3)+c1*this._determinant2x2(a2,a3,b2,b3)};CanvasMatrix4.prototype._determinant4x4=function(){var a1=this.m11;var b1=this.m12;var c1=this.m13;var d1=this.m14;var a2=this.m21;var b2=this.m22;var c2=this.m23;var d2=this.m24;var a3=this.m31;var b3=this.m32;var c3=this.m33;var d3=this.m34;var a4=this.m41;var b4=this.m42;var c4=this.m43;var d4=this.m44;return a1*this._determinant3x3(b2,b3,b4,c2,c3,c4,d2,d3,d4)-b1*this._determinant3x3(a2,a3,a4,c2,c3,c4,d2,d3,d4)+c1*this._determinant3x3(a2,a3,a4,b2,b3,b4,d2,d3,d4)-d1*this._determinant3x3(a2,a3,a4,b2,b3,b4,c2,c3,c4)};CanvasMatrix4.prototype._makeAdjoint=function(){var a1=this.m11;var b1=this.m12;var c1=this.m13;var d1=this.m14;var a2=this.m21;var b2=this.m22;var c2=this.m23;var d2=this.m24;var a3=this.m31;var b3=this.m32;var c3=this.m33;var d3=this.m34;var a4=this.m41;var b4=this.m42;var c4=this.m43;var d4=this.m44;this.m11=this._determinant3x3(b2,b3,b4,c2,c3,c4,d2,d3,d4);this.m21=-this._determinant3x3(a2,a3,a4,c2,c3,c4,d2,d3,d4);this.m31=this._determinant3x3(a2,a3,a4,b2,b3,b4,d2,d3,d4);this.m41=-this._determinant3x3(a2,a3,a4,b2,b3,b4,c2,c3,c4);this.m12=-this._determinant3x3(b1,b3,b4,c1,c3,c4,d1,d3,d4);this.m22=this._determinant3x3(a1,a3,a4,c1,c3,c4,d1,d3,d4);this.m32=-this._determinant3x3(a1,a3,a4,b1,b3,b4,d1,d3,d4);this.m42=this._determinant3x3(a1,a3,a4,b1,b3,b4,c1,c3,c4);this.m13=this._determinant3x3(b1,b2,b4,c1,c2,c4,d1,d2,d4);this.m23=-this._determinant3x3(a1,a2,a4,c1,c2,c4,d1,d2,d4);this.m33=this._determinant3x3(a1,a2,a4,b1,b2,b4,d1,d2,d4);this.m43=-this._determinant3x3(a1,a2,a4,b1,b2,b4,c1,c2,c4);this.m14=-this._determinant3x3(b1,b2,b3,c1,c2,c3,d1,d2,d3);this.m24=this._determinant3x3(a1,a2,a3,c1,c2,c3,d1,d2,d3);this.m34=-this._determinant3x3(a1,a2,a3,b1,b2,b3,d1,d2,d3);this.m44=this._determinant3x3(a1,a2,a3,b1,b2,b3,c1,c2,c3)}
</script>

## The Schloss Lab

---

<img src="assets/img/labphoto.jpg" style="margin:0px auto;display:block" width="800">

---

## We are interested in understanding...

> * the forces that shape microbial communities
> * why that variation matters

---

<img src="assets/img/sarahruthsheep.jpg" style="margin:0px auto;display:block" width="800">

---

## Some questions that we have that you probably do too

> * Why do we see the diversity that we do within our communities?
> * Why are instances of these communities so different?
> * What if we could take community X from environment A and put it in
environment B?
> * What if we could take community X and start over in environment A?
> * Can we change the direction that community X takes to make it look more
like community Y?

--- &twocol

## Oh yeah - we do this in the gut

*** {name: left}
<img src="http://laughingsquid.com/wp-content/uploads/gi-metro-t-shirt.jpg" style="margin:0px auto;display:block" width="400">

*** {name: right}
> * It contains a tractable microbial "community"
> * Non-human systems are fairly reproducible
> * Easy to perturb (antibiotics, diet)
> * Numerous phenotypes (disease models)
> * Can generate environments (genetics)
> * Can generate communities (germ-free)

---

## Why do we observe the diversity we do in the gut?

> * Genetics/Evolution
> * Diet (e.g. vegan vs. SuperSizeMe)
> * Environmental exposures (e.g. rural vs. urban)
> * Life history (e.g. breast vs. bottle fed, antibiotics)
> * Immune system
> * Very difficult to separate these forces to determine their relative
importance

---

## Shocker: Ecologists have thought about this too!

* **Neutral theory (Hubbell):** The differences between trophically similar
organisms are not important and the observed biodiversity is the product of
each species taking a random walk (e.g. Island biogeography)
* **Community assembly rules (Diamond):** Competition is the primary force that
shapes the structure of communities and populations will seek to minimize niche
overlap (e.g. Forest succession)

>* Should sound analogous to anyone familiar with the rift between the neutral
and selection-based models of molecular evolution. The truth is somewhere in the
middle

--- .segue .dark

## Experimental systems for studying the formation of host-associated communities

---

## Neonate gut
<img src="http://www.plosbiology.org/article/fetchObject.action?uri=info:doi/10.1371/journal.pbio.0050177.g007&representation=PNG_M" style="margin:0px auto;display:block" width="500">

#  Palmer et al. (2007) PLoS Biology

---

<img src="assets/img/KoenigSuccession.png" style="margin:0px auto;display:block" width="700">

--- &twocol

## Sympatric populations of *Peromyscus* spp.

***{name: left}
* Unable to differentiate between sympatric species of mice (not a novel result)
* Diet does not explain variation
* Physiological state does not explain variation
* "Personalized" signal of community is lost within a week

# Baxter et al. (2014) AEM *in review*

***{name: right}

<img src="assets/fig/unnamed-chunk-1-1.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />


---

## Sympatric populations of *Peromyscus* spp.

<canvas id="unnamed_chunk_2textureCanvas" style="display: none;" width="256" height="256">
Your browser does not support the HTML5 canvas element.</canvas>
<!-- ****** spheres object 18 ****** -->
<script id="unnamed_chunk_2vshader18" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
attribute vec3 aNorm;
uniform mat4 normMatrix;
varying vec3 vNormal;
void main(void) {
vPosition = mvMatrix * vec4(aPos, 1.);
gl_Position = prMatrix * vPosition;
vCol = aCol;
vNormal = normalize((normMatrix * vec4(aNorm, 1.)).xyz);
}
</script>
<script id="unnamed_chunk_2fshader18" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
varying vec3 vNormal;
void main(void) {
vec3 eye = normalize(-vPosition.xyz);
const vec3 emission = vec3(0., 0., 0.);
const vec3 ambient1 = vec3(0., 0., 0.);
const vec3 specular1 = vec3(1., 1., 1.);// light*material
const float shininess1 = 50.;
vec4 colDiff1 = vec4(vCol.rgb * vec3(1., 1., 1.), vCol.a);
const vec3 lightDir1 = vec3(0., 0., 1.);
vec3 halfVec1 = normalize(lightDir1 + eye);
vec4 lighteffect = vec4(emission, 0.);
vec3 n = normalize(vNormal);
n = -faceforward(n, n, eye);
vec3 col1 = ambient1;
float nDotL1 = dot(n, lightDir1);
col1 = col1 + max(nDotL1, 0.) * colDiff1.rgb;
col1 = col1 + pow(max(dot(halfVec1, n), 0.), shininess1) * specular1;
lighteffect = lighteffect + vec4(col1, colDiff1.a);
gl_FragColor = lighteffect;
}
</script> 
<!-- ****** text object 20 ****** -->
<script id="unnamed_chunk_2vshader20" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
attribute vec2 aTexcoord;
varying vec2 vTexcoord;
attribute vec2 aOfs;
void main(void) {
vCol = aCol;
vTexcoord = aTexcoord;
vec4 pos = prMatrix * mvMatrix * vec4(aPos, 1.);
pos = pos/pos.w;
gl_Position = pos + vec4(aOfs, 0.,0.);
}
</script>
<script id="unnamed_chunk_2fshader20" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
varying vec2 vTexcoord;
uniform sampler2D uSampler;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
vec4 textureColor = lighteffect*texture2D(uSampler, vTexcoord);
if (textureColor.a < 0.1)
discard;
else
gl_FragColor = textureColor;
}
</script> 
<!-- ****** text object 21 ****** -->
<script id="unnamed_chunk_2vshader21" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
attribute vec2 aTexcoord;
varying vec2 vTexcoord;
attribute vec2 aOfs;
void main(void) {
vCol = aCol;
vTexcoord = aTexcoord;
vec4 pos = prMatrix * mvMatrix * vec4(aPos, 1.);
pos = pos/pos.w;
gl_Position = pos + vec4(aOfs, 0.,0.);
}
</script>
<script id="unnamed_chunk_2fshader21" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
varying vec2 vTexcoord;
uniform sampler2D uSampler;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
vec4 textureColor = lighteffect*texture2D(uSampler, vTexcoord);
if (textureColor.a < 0.1)
discard;
else
gl_FragColor = textureColor;
}
</script> 
<!-- ****** text object 22 ****** -->
<script id="unnamed_chunk_2vshader22" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
attribute vec2 aTexcoord;
varying vec2 vTexcoord;
attribute vec2 aOfs;
void main(void) {
vCol = aCol;
vTexcoord = aTexcoord;
vec4 pos = prMatrix * mvMatrix * vec4(aPos, 1.);
pos = pos/pos.w;
gl_Position = pos + vec4(aOfs, 0.,0.);
}
</script>
<script id="unnamed_chunk_2fshader22" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
varying vec2 vTexcoord;
uniform sampler2D uSampler;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
vec4 textureColor = lighteffect*texture2D(uSampler, vTexcoord);
if (textureColor.a < 0.1)
discard;
else
gl_FragColor = textureColor;
}
</script> 
<!-- ****** lines object 23 ****** -->
<script id="unnamed_chunk_2vshader23" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
void main(void) {
vPosition = mvMatrix * vec4(aPos, 1.);
gl_Position = prMatrix * vPosition;
vCol = aCol;
}
</script>
<script id="unnamed_chunk_2fshader23" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
gl_FragColor = lighteffect;
}
</script> 
<!-- ****** text object 24 ****** -->
<script id="unnamed_chunk_2vshader24" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
attribute vec2 aTexcoord;
varying vec2 vTexcoord;
attribute vec2 aOfs;
void main(void) {
vCol = aCol;
vTexcoord = aTexcoord;
vec4 pos = prMatrix * mvMatrix * vec4(aPos, 1.);
pos = pos/pos.w;
gl_Position = pos + vec4(aOfs, 0.,0.);
}
</script>
<script id="unnamed_chunk_2fshader24" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
varying vec2 vTexcoord;
uniform sampler2D uSampler;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
vec4 textureColor = lighteffect*texture2D(uSampler, vTexcoord);
if (textureColor.a < 0.1)
discard;
else
gl_FragColor = textureColor;
}
</script> 
<!-- ****** lines object 25 ****** -->
<script id="unnamed_chunk_2vshader25" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
void main(void) {
vPosition = mvMatrix * vec4(aPos, 1.);
gl_Position = prMatrix * vPosition;
vCol = aCol;
}
</script>
<script id="unnamed_chunk_2fshader25" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
gl_FragColor = lighteffect;
}
</script> 
<!-- ****** text object 26 ****** -->
<script id="unnamed_chunk_2vshader26" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
attribute vec2 aTexcoord;
varying vec2 vTexcoord;
attribute vec2 aOfs;
void main(void) {
vCol = aCol;
vTexcoord = aTexcoord;
vec4 pos = prMatrix * mvMatrix * vec4(aPos, 1.);
pos = pos/pos.w;
gl_Position = pos + vec4(aOfs, 0.,0.);
}
</script>
<script id="unnamed_chunk_2fshader26" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
varying vec2 vTexcoord;
uniform sampler2D uSampler;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
vec4 textureColor = lighteffect*texture2D(uSampler, vTexcoord);
if (textureColor.a < 0.1)
discard;
else
gl_FragColor = textureColor;
}
</script> 
<!-- ****** lines object 27 ****** -->
<script id="unnamed_chunk_2vshader27" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
void main(void) {
vPosition = mvMatrix * vec4(aPos, 1.);
gl_Position = prMatrix * vPosition;
vCol = aCol;
}
</script>
<script id="unnamed_chunk_2fshader27" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
gl_FragColor = lighteffect;
}
</script> 
<!-- ****** text object 28 ****** -->
<script id="unnamed_chunk_2vshader28" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
attribute vec2 aTexcoord;
varying vec2 vTexcoord;
attribute vec2 aOfs;
void main(void) {
vCol = aCol;
vTexcoord = aTexcoord;
vec4 pos = prMatrix * mvMatrix * vec4(aPos, 1.);
pos = pos/pos.w;
gl_Position = pos + vec4(aOfs, 0.,0.);
}
</script>
<script id="unnamed_chunk_2fshader28" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
varying vec2 vTexcoord;
uniform sampler2D uSampler;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
vec4 textureColor = lighteffect*texture2D(uSampler, vTexcoord);
if (textureColor.a < 0.1)
discard;
else
gl_FragColor = textureColor;
}
</script> 
<!-- ****** lines object 29 ****** -->
<script id="unnamed_chunk_2vshader29" type="x-shader/x-vertex">
attribute vec3 aPos;
attribute vec4 aCol;
uniform mat4 mvMatrix;
uniform mat4 prMatrix;
varying vec4 vCol;
varying vec4 vPosition;
void main(void) {
vPosition = mvMatrix * vec4(aPos, 1.);
gl_Position = prMatrix * vPosition;
vCol = aCol;
}
</script>
<script id="unnamed_chunk_2fshader29" type="x-shader/x-fragment"> 
#ifdef GL_ES
precision highp float;
#endif
varying vec4 vCol; // carries alpha
varying vec4 vPosition;
void main(void) {
vec4 colDiff = vCol;
vec4 lighteffect = colDiff;
gl_FragColor = lighteffect;
}
</script> 
<script type="text/javascript"> 
function getShader ( gl, id ){
var shaderScript = document.getElementById ( id );
var str = "";
var k = shaderScript.firstChild;
while ( k ){
if ( k.nodeType == 3 ) str += k.textContent;
k = k.nextSibling;
}
var shader;
if ( shaderScript.type == "x-shader/x-fragment" )
shader = gl.createShader ( gl.FRAGMENT_SHADER );
else if ( shaderScript.type == "x-shader/x-vertex" )
shader = gl.createShader(gl.VERTEX_SHADER);
else return null;
gl.shaderSource(shader, str);
gl.compileShader(shader);
if (gl.getShaderParameter(shader, gl.COMPILE_STATUS) == 0)
alert(gl.getShaderInfoLog(shader));
return shader;
}
var min = Math.min;
var max = Math.max;
var sqrt = Math.sqrt;
var sin = Math.sin;
var acos = Math.acos;
var tan = Math.tan;
var SQRT2 = Math.SQRT2;
var PI = Math.PI;
var log = Math.log;
var exp = Math.exp;
function unnamed_chunk_2webGLStart() {
var debug = function(msg) {
document.getElementById("unnamed_chunk_2debug").innerHTML = msg;
}
debug("");
var canvas = document.getElementById("unnamed_chunk_2canvas");
if (!window.WebGLRenderingContext){
debug(" Your browser does not support WebGL. See <a href=\"http://get.webgl.org\">http://get.webgl.org</a>");
return;
}
var gl;
try {
// Try to grab the standard context. If it fails, fallback to experimental.
gl = canvas.getContext("webgl") 
|| canvas.getContext("experimental-webgl");
}
catch(e) {}
if ( !gl ) {
debug(" Your browser appears to support WebGL, but did not create a WebGL context.  See <a href=\"http://get.webgl.org\">http://get.webgl.org</a>");
return;
}
var width = 505;  var height = 505;
canvas.width = width;   canvas.height = height;
gl.viewport(0, 0, width, height);
var prMatrix = new CanvasMatrix4();
var mvMatrix = new CanvasMatrix4();
var normMatrix = new CanvasMatrix4();
var saveMat = new CanvasMatrix4();
saveMat.makeIdentity();
var distance;
var posLoc = 0;
var colLoc = 1;
var zoom = 1;
var fov = 30;
var userMatrix = new CanvasMatrix4();
userMatrix.load([
1, 0, 0, 0,
0, 0.3420201, -0.9396926, 0,
0, 0.9396926, 0.3420201, 0,
0, 0, 0, 1
]);
function getPowerOfTwo(value) {
var pow = 1;
while(pow<value) {
pow *= 2;
}
return pow;
}
function handleLoadedTexture(texture, textureCanvas) {
gl.pixelStorei(gl.UNPACK_FLIP_Y_WEBGL, true);
gl.bindTexture(gl.TEXTURE_2D, texture);
gl.texImage2D(gl.TEXTURE_2D, 0, gl.RGBA, gl.RGBA, gl.UNSIGNED_BYTE, textureCanvas);
gl.texParameteri(gl.TEXTURE_2D, gl.TEXTURE_MAG_FILTER, gl.LINEAR);
gl.texParameteri(gl.TEXTURE_2D, gl.TEXTURE_MIN_FILTER, gl.LINEAR_MIPMAP_NEAREST);
gl.generateMipmap(gl.TEXTURE_2D);
gl.bindTexture(gl.TEXTURE_2D, null);
}
function loadImageToTexture(filename, texture) {   
var canvas = document.getElementById("unnamed_chunk_2textureCanvas");
var ctx = canvas.getContext("2d");
var image = new Image();
image.onload = function() {
var w = image.width;
var h = image.height;
var canvasX = getPowerOfTwo(w);
var canvasY = getPowerOfTwo(h);
canvas.width = canvasX;
canvas.height = canvasY;
ctx.imageSmoothingEnabled = true;
ctx.drawImage(image, 0, 0, canvasX, canvasY);
handleLoadedTexture(texture, canvas);
drawScene();
}
image.src = filename;
}  	   
function drawTextToCanvas(text, cex) {
var canvasX, canvasY;
var textX, textY;
var textHeight = 20 * cex;
var textColour = "white";
var fontFamily = "Arial";
var backgroundColour = "rgba(0,0,0,0)";
var canvas = document.getElementById("unnamed_chunk_2textureCanvas");
var ctx = canvas.getContext("2d");
ctx.font = textHeight+"px "+fontFamily;
canvasX = 1;
var widths = [];
for (var i = 0; i < text.length; i++)  {
widths[i] = ctx.measureText(text[i]).width;
canvasX = (widths[i] > canvasX) ? widths[i] : canvasX;
}	  
canvasX = getPowerOfTwo(canvasX);
var offset = 2*textHeight; // offset to first baseline
var skip = 2*textHeight;   // skip between baselines	  
canvasY = getPowerOfTwo(offset + text.length*skip);
canvas.width = canvasX;
canvas.height = canvasY;
ctx.fillStyle = backgroundColour;
ctx.fillRect(0, 0, ctx.canvas.width, ctx.canvas.height);
ctx.fillStyle = textColour;
ctx.textAlign = "left";
ctx.textBaseline = "alphabetic";
ctx.font = textHeight+"px "+fontFamily;
for(var i = 0; i < text.length; i++) {
textY = i*skip + offset;
ctx.fillText(text[i], 0,  textY);
}
return {canvasX:canvasX, canvasY:canvasY,
widths:widths, textHeight:textHeight,
offset:offset, skip:skip};
}
// ****** sphere object ******
var v=new Float32Array([
-1, 0, 0,
1, 0, 0,
0, -1, 0,
0, 1, 0,
0, 0, -1,
0, 0, 1,
-0.7071068, 0, -0.7071068,
-0.7071068, -0.7071068, 0,
0, -0.7071068, -0.7071068,
-0.7071068, 0, 0.7071068,
0, -0.7071068, 0.7071068,
-0.7071068, 0.7071068, 0,
0, 0.7071068, -0.7071068,
0, 0.7071068, 0.7071068,
0.7071068, -0.7071068, 0,
0.7071068, 0, -0.7071068,
0.7071068, 0, 0.7071068,
0.7071068, 0.7071068, 0,
-0.9349975, 0, -0.3546542,
-0.9349975, -0.3546542, 0,
-0.77044, -0.4507894, -0.4507894,
0, -0.3546542, -0.9349975,
-0.3546542, 0, -0.9349975,
-0.4507894, -0.4507894, -0.77044,
-0.3546542, -0.9349975, 0,
0, -0.9349975, -0.3546542,
-0.4507894, -0.77044, -0.4507894,
-0.9349975, 0, 0.3546542,
-0.77044, -0.4507894, 0.4507894,
0, -0.9349975, 0.3546542,
-0.4507894, -0.77044, 0.4507894,
-0.3546542, 0, 0.9349975,
0, -0.3546542, 0.9349975,
-0.4507894, -0.4507894, 0.77044,
-0.9349975, 0.3546542, 0,
-0.77044, 0.4507894, -0.4507894,
0, 0.9349975, -0.3546542,
-0.3546542, 0.9349975, 0,
-0.4507894, 0.77044, -0.4507894,
0, 0.3546542, -0.9349975,
-0.4507894, 0.4507894, -0.77044,
-0.77044, 0.4507894, 0.4507894,
0, 0.3546542, 0.9349975,
-0.4507894, 0.4507894, 0.77044,
0, 0.9349975, 0.3546542,
-0.4507894, 0.77044, 0.4507894,
0.9349975, -0.3546542, 0,
0.9349975, 0, -0.3546542,
0.77044, -0.4507894, -0.4507894,
0.3546542, -0.9349975, 0,
0.4507894, -0.77044, -0.4507894,
0.3546542, 0, -0.9349975,
0.4507894, -0.4507894, -0.77044,
0.9349975, 0, 0.3546542,
0.77044, -0.4507894, 0.4507894,
0.3546542, 0, 0.9349975,
0.4507894, -0.4507894, 0.77044,
0.4507894, -0.77044, 0.4507894,
0.9349975, 0.3546542, 0,
0.77044, 0.4507894, -0.4507894,
0.4507894, 0.4507894, -0.77044,
0.3546542, 0.9349975, 0,
0.4507894, 0.77044, -0.4507894,
0.77044, 0.4507894, 0.4507894,
0.4507894, 0.77044, 0.4507894,
0.4507894, 0.4507894, 0.77044
]);
var f=new Uint16Array([
0, 18, 19,
6, 20, 18,
7, 19, 20,
19, 18, 20,
4, 21, 22,
8, 23, 21,
6, 22, 23,
22, 21, 23,
2, 24, 25,
7, 26, 24,
8, 25, 26,
25, 24, 26,
7, 20, 26,
6, 23, 20,
8, 26, 23,
26, 20, 23,
0, 19, 27,
7, 28, 19,
9, 27, 28,
27, 19, 28,
2, 29, 24,
10, 30, 29,
7, 24, 30,
24, 29, 30,
5, 31, 32,
9, 33, 31,
10, 32, 33,
32, 31, 33,
9, 28, 33,
7, 30, 28,
10, 33, 30,
33, 28, 30,
0, 34, 18,
11, 35, 34,
6, 18, 35,
18, 34, 35,
3, 36, 37,
12, 38, 36,
11, 37, 38,
37, 36, 38,
4, 22, 39,
6, 40, 22,
12, 39, 40,
39, 22, 40,
6, 35, 40,
11, 38, 35,
12, 40, 38,
40, 35, 38,
0, 27, 34,
9, 41, 27,
11, 34, 41,
34, 27, 41,
5, 42, 31,
13, 43, 42,
9, 31, 43,
31, 42, 43,
3, 37, 44,
11, 45, 37,
13, 44, 45,
44, 37, 45,
11, 41, 45,
9, 43, 41,
13, 45, 43,
45, 41, 43,
1, 46, 47,
14, 48, 46,
15, 47, 48,
47, 46, 48,
2, 25, 49,
8, 50, 25,
14, 49, 50,
49, 25, 50,
4, 51, 21,
15, 52, 51,
8, 21, 52,
21, 51, 52,
15, 48, 52,
14, 50, 48,
8, 52, 50,
52, 48, 50,
1, 53, 46,
16, 54, 53,
14, 46, 54,
46, 53, 54,
5, 32, 55,
10, 56, 32,
16, 55, 56,
55, 32, 56,
2, 49, 29,
14, 57, 49,
10, 29, 57,
29, 49, 57,
14, 54, 57,
16, 56, 54,
10, 57, 56,
57, 54, 56,
1, 47, 58,
15, 59, 47,
17, 58, 59,
58, 47, 59,
4, 39, 51,
12, 60, 39,
15, 51, 60,
51, 39, 60,
3, 61, 36,
17, 62, 61,
12, 36, 62,
36, 61, 62,
17, 59, 62,
15, 60, 59,
12, 62, 60,
62, 59, 60,
1, 58, 53,
17, 63, 58,
16, 53, 63,
53, 58, 63,
3, 44, 61,
13, 64, 44,
17, 61, 64,
61, 44, 64,
5, 55, 42,
16, 65, 55,
13, 42, 65,
42, 55, 65,
16, 63, 65,
17, 64, 63,
13, 65, 64,
65, 63, 64
]);
var sphereBuf = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, sphereBuf);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var sphereIbuf = gl.createBuffer();
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, sphereIbuf);
gl.bufferData(gl.ELEMENT_ARRAY_BUFFER, f, gl.STATIC_DRAW);
// ****** spheres object 18 ******
var prog18  = gl.createProgram();
gl.attachShader(prog18, getShader( gl, "unnamed_chunk_2vshader18" ));
gl.attachShader(prog18, getShader( gl, "unnamed_chunk_2fshader18" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog18, 0, "aPos");
gl.bindAttribLocation(prog18, 1, "aCol");
gl.linkProgram(prog18);
var v=new Float32Array([
0.59924, 0.126801, 0.058711, 0, 0, 1, 1, 0.022384,
0.483542, -0.067833, 0.114563, 0, 0, 1, 1, 0.022384,
0.317529, 0.403562, -0.082314, 0, 0, 1, 1, 0.022384,
-0.2681, -0.616393, 0.303138, 0, 0, 1, 1, 0.022384,
-0.424707, 0.107711, -0.277282, 1, 0, 0, 1, 0.022384,
-0.113082, -0.074271, 0.543943, 0, 0, 1, 1, 0.022384,
0.318532, 0.439042, 0.512828, 0, 0, 1, 1, 0.022384,
0.031541, 0.535551, -0.137665, 0, 0, 1, 1, 0.022384,
0.056679, 0.645257, 0.038865, 0, 0, 1, 1, 0.022384,
-0.092315, 0.193655, -0.346143, 0, 0, 1, 1, 0.022384,
-0.338957, -0.318806, -0.417409, 1, 0, 0, 1, 0.022384,
-0.457238, -0.197526, 0.10871, 1, 0, 0, 1, 0.022384,
0.547039, -0.201387, 0.069836, 0, 0, 1, 1, 0.022384,
-0.412096, -0.092468, -0.235798, 0, 0, 1, 1, 0.022384,
0.440282, -0.368102, -0.358996, 1, 0, 0, 1, 0.022384,
0.486996, -0.262675, -0.171978, 0, 0, 1, 1, 0.022384,
0.363616, -0.276497, -0.052852, 0, 0, 1, 1, 0.022384,
0.208856, -0.327826, -0.162454, 0, 0, 1, 1, 0.022384,
0.440547, 0.368616, -0.181741, 1, 0, 0, 1, 0.022384,
0.107748, 0.499506, 0.215932, 0, 0, 1, 1, 0.022384,
-0.409915, -0.357001, -0.41916, 0, 0, 1, 1, 0.022384,
0.001187, -0.634009, -0.220438, 0, 0, 1, 1, 0.022384,
0.305904, 0.227984, 0.190731, 1, 0, 0, 1, 0.022384,
0.287931, -0.381739, 0.342945, 0, 0, 1, 1, 0.022384,
-0.460835, -0.318658, 0.248886, 0, 0, 1, 1, 0.022384,
0.468017, -0.113659, 0.301087, 1, 0, 0, 1, 0.022384,
0.022716, -0.460219, 0.425742, 0, 0, 1, 1, 0.022384,
0.343885, 0.220362, -0.444271, 0, 0, 1, 1, 0.022384,
0.433417, -0.375109, -0.376308, 1, 0, 0, 1, 0.022384,
0.504961, 0.102933, -0.182121, 0, 0, 1, 1, 0.022384,
0.259918, 0.288809, -0.235531, 1, 0, 0, 1, 0.022384,
0.377973, -0.295048, 0.351069, 0, 0, 1, 1, 0.022384,
-0.346265, -0.336155, -0.42078, 1, 0, 0, 1, 0.022384,
0.517409, 0.00363, -0.199147, 1, 0, 0, 1, 0.022384,
0.444166, -0.359289, -0.329929, 1, 0, 0, 1, 0.022384,
-0.137328, -0.482377, 0.354363, 1, 0, 0, 1, 0.022384,
0.307712, -0.268748, -0.278548, 0, 0, 1, 1, 0.022384,
-0.024932, 0.226906, -0.038733, 1, 0, 0, 1, 0.022384,
-0.322495, 0.278656, 0.191406, 0, 0, 1, 1, 0.022384,
0.47407, 0.41811, 0.242964, 0, 0, 1, 1, 0.022384,
0.298735, 0.390386, -0.339778, 1, 0, 0, 1, 0.022384,
0.535323, 0.058247, 0.170793, 0, 0, 1, 1, 0.022384,
0.140509, 0.693543, -0.153307, 1, 0, 0, 1, 0.022384,
0.373567, 0.319637, -0.326015, 0, 0, 1, 1, 0.022384,
-0.214184, 0.189955, 0.43219, 1, 0, 0, 1, 0.022384,
-0.382345, -0.336212, -0.417548, 1, 0, 0, 1, 0.022384,
-0.44071, 0.490441, -0.01962, 1, 0, 0, 1, 0.022384,
0.463154, -0.358768, -0.311954, 1, 0, 0, 1, 0.022384,
-0.571562, 0.00988, -0.179362, 0, 0, 1, 1, 0.022384,
-0.269353, 0.051424, 0.183162, 1, 0, 0, 1, 0.022384,
-0.329571, -0.717591, 0.066804, 1, 0, 0, 1, 0.022384,
0.241981, -0.60176, -0.118221, 1, 0, 0, 1, 0.022384,
-0.406087, -0.383461, -0.42015, 1, 0, 0, 1, 0.022384,
0.400634, -0.109909, 0.440159, 1, 0, 0, 1, 0.022384,
-0.109948, -0.319528, 0.221516, 0, 0, 1, 1, 0.022384,
0.249625, 0.178829, -0.215639, 1, 0, 0, 1, 0.022384,
-0.152742, 0.663325, -0.127527, 1, 0, 0, 1, 0.022384,
-0.334404, -0.296829, 0.42776, 0, 0, 1, 1, 0.022384,
-0.50118, 0.184038, -0.065318, 1, 0, 0, 1, 0.022384,
-0.320685, 0.561285, 0.145301, 1, 0, 0, 1, 0.022384,
-0.37318, 0.005043, -0.388094, 1, 0, 0, 1, 0.022384,
0.065525, -0.692767, -0.008008, 0, 0, 1, 1, 0.022384,
0.3289, 0.010205, 0.457957, 0, 0, 1, 1, 0.022384,
-0.338749, -0.01471, 0.340103, 0, 0, 1, 1, 0.022384,
0.230857, 0.563554, 0.310617, 0, 0, 1, 1, 0.022384,
-0.007091, 0.126121, -0.738894, 0, 0, 1, 1, 0.022384,
-0.28672, -0.118053, 0.192536, 0, 0, 1, 1, 0.022384,
-0.133388, 0.416972, 0.137303, 0, 0, 1, 1, 0.022384,
0.492067, 0.208251, 0.391905, 1, 0, 0, 1, 0.022384,
0.445602, -0.136645, 0.144873, 1, 0, 0, 1, 0.022384,
0.447274, -0.055401, -0.155615, 1, 0, 0, 1, 0.022384,
0.092618, -0.639909, -0.050216, 1, 0, 0, 1, 0.022384,
-0.184553, 0.098803, -0.333237, 1, 0, 0, 1, 0.022384,
0.13231, 0.277432, -0.578401, 1, 0, 0, 1, 0.022384,
-0.386588, -0.064578, -0.242515, 1, 0, 0, 1, 0.022384,
0.066559, 0.201512, -0.395504, 1, 0, 0, 1, 0.022384,
0.049215, -0.134763, 0.458552, 0, 0, 1, 1, 0.022384,
0.023378, -0.122923, 0.535558, 0, 0, 1, 1, 0.022384,
-0.185045, 0.472669, -0.212666, 0, 0, 1, 1, 0.022384,
-0.288929, -0.171493, 0.443746, 0, 0, 1, 1, 0.022384,
-0.46527, -0.203599, -0.362905, 1, 0, 0, 1, 0.022384,
-0.174128, 0.207089, 0.508808, 0, 0, 1, 1, 0.022384,
0.228384, -0.253832, -0.675965, 1, 0, 0, 1, 0.022384,
-0.339798, 0.176858, -0.557689, 0, 0, 1, 1, 0.022384,
-0.482458, 0.312058, 0.302037, 0, 0, 1, 1, 0.022384,
0.209178, -0.337945, -0.33976, 1, 0, 0, 1, 0.022384,
-0.016838, 0.06674, 0.664219, 1, 0, 0, 1, 0.022384,
-0.290733, 0.012032, -0.354356, 1, 0, 0, 1, 0.022384,
-0.466099, 0.283297, -0.057631, 0, 0, 1, 1, 0.022384,
-0.391716, -0.359099, -0.420913, 1, 0, 0, 1, 0.022384,
-0.26283, 0.538979, -0.444956, 1, 0, 0, 1, 0.022384,
-0.169504, 0.518912, 0.316745, 0, 0, 1, 1, 0.022384,
-0.522505, 0.031168, -0.078697, 1, 0, 0, 1, 0.022384,
-0.605435, -0.046916, 0.121699, 1, 0, 0, 1, 0.022384,
-0.074792, 0.500103, 0.46318, 1, 0, 0, 1, 0.022384,
0.356459, 0.579291, 0.113671, 1, 0, 0, 1, 0.022384,
-0.261945, -0.174713, -0.397933, 0, 0, 1, 1, 0.022384,
-0.067258, 0.035831, 0.644229, 0, 0, 1, 1, 0.022384,
-0.53982, -0.110677, -0.139336, 0, 0, 1, 1, 0.022384,
0.155173, 0.414209, -0.451083, 0, 0, 1, 1, 0.022384,
-0.194588, -0.070442, 0.58395, 0, 0, 1, 1, 0.022384,
-0.459425, 0.075589, -0.185502, 0, 0, 1, 1, 0.022384,
-0.466476, 0.161233, 0.26505, 0, 0, 1, 1, 0.022384,
0.223747, -0.69245, 0.360508, 1, 0, 0, 1, 0.022384,
-0.271176, -0.087094, 0.573907, 0, 0, 1, 1, 0.022384,
0.24605, -0.188672, -0.092787, 1, 0, 0, 1, 0.022384,
0.244152, -0.623954, -0.172987, 1, 0, 0, 1, 0.022384,
0.345051, 0.295953, 0.449771, 0, 0, 1, 1, 0.022384,
0.302505, 0.213043, -0.392812, 1, 0, 0, 1, 0.022384,
-0.126833, -0.121583, 0.620012, 0, 0, 1, 1, 0.022384,
0.134962, 0.051043, 0.388158, 0, 0, 1, 1, 0.022384
]);
var values18 = v;
var normLoc18 = gl.getAttribLocation(prog18, "aNorm");
var mvMatLoc18 = gl.getUniformLocation(prog18,"mvMatrix");
var prMatLoc18 = gl.getUniformLocation(prog18,"prMatrix");
var normMatLoc18 = gl.getUniformLocation(prog18,"normMatrix");
// ****** text object 20 ******
var prog20  = gl.createProgram();
gl.attachShader(prog20, getShader( gl, "unnamed_chunk_2vshader20" ));
gl.attachShader(prog20, getShader( gl, "unnamed_chunk_2fshader20" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog20, 0, "aPos");
gl.bindAttribLocation(prog20, 1, "aCol");
gl.linkProgram(prog20);
var texts = [
"Axis 1"
];
var texinfo = drawTextToCanvas(texts, 1);	 
var canvasX20 = texinfo.canvasX;
var canvasY20 = texinfo.canvasY;
var ofsLoc20 = gl.getAttribLocation(prog20, "aOfs");
var texture20 = gl.createTexture();
var texLoc20 = gl.getAttribLocation(prog20, "aTexcoord");
var sampler20 = gl.getUniformLocation(prog20,"uSampler");
handleLoadedTexture(texture20, document.getElementById("unnamed_chunk_2textureCanvas"));
var v=new Float32Array([
-0.003097504, -0.98827, -1.008034, 0, -0.5, 0.5, 0.5,
-0.003097504, -0.98827, -1.008034, 1, -0.5, 0.5, 0.5,
-0.003097504, -0.98827, -1.008034, 1, 1.5, 0.5, 0.5,
-0.003097504, -0.98827, -1.008034, 0, 1.5, 0.5, 0.5
]);
for (var i=0; i<1; i++) 
for (var j=0; j<4; j++) {
ind = 7*(4*i + j) + 3;
v[ind+2] = 2*(v[ind]-v[ind+2])*texinfo.widths[i]/width;
v[ind+3] = 2*(v[ind+1]-v[ind+3])*texinfo.textHeight/height;
v[ind] *= texinfo.widths[i]/texinfo.canvasX;
v[ind+1] = 1.0-(texinfo.offset + i*texinfo.skip 
- v[ind+1]*texinfo.textHeight)/texinfo.canvasY;
}
var f=new Uint16Array([
0, 1, 2, 0, 2, 3
]);
var buf20 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf20);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var ibuf20 = gl.createBuffer();
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf20);
gl.bufferData(gl.ELEMENT_ARRAY_BUFFER, f, gl.STATIC_DRAW);
var mvMatLoc20 = gl.getUniformLocation(prog20,"mvMatrix");
var prMatLoc20 = gl.getUniformLocation(prog20,"prMatrix");
// ****** text object 21 ******
var prog21  = gl.createProgram();
gl.attachShader(prog21, getShader( gl, "unnamed_chunk_2vshader21" ));
gl.attachShader(prog21, getShader( gl, "unnamed_chunk_2fshader21" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog21, 0, "aPos");
gl.bindAttribLocation(prog21, 1, "aCol");
gl.linkProgram(prog21);
var texts = [
"Axis 2"
];
var texinfo = drawTextToCanvas(texts, 1);	 
var canvasX21 = texinfo.canvasX;
var canvasY21 = texinfo.canvasY;
var ofsLoc21 = gl.getAttribLocation(prog21, "aOfs");
var texture21 = gl.createTexture();
var texLoc21 = gl.getAttribLocation(prog21, "aTexcoord");
var sampler21 = gl.getUniformLocation(prog21,"uSampler");
handleLoadedTexture(texture21, document.getElementById("unnamed_chunk_2textureCanvas"));
var v=new Float32Array([
-0.8365118, -0.01202399, -1.008034, 0, -0.5, 0.5, 0.5,
-0.8365118, -0.01202399, -1.008034, 1, -0.5, 0.5, 0.5,
-0.8365118, -0.01202399, -1.008034, 1, 1.5, 0.5, 0.5,
-0.8365118, -0.01202399, -1.008034, 0, 1.5, 0.5, 0.5
]);
for (var i=0; i<1; i++) 
for (var j=0; j<4; j++) {
ind = 7*(4*i + j) + 3;
v[ind+2] = 2*(v[ind]-v[ind+2])*texinfo.widths[i]/width;
v[ind+3] = 2*(v[ind+1]-v[ind+3])*texinfo.textHeight/height;
v[ind] *= texinfo.widths[i]/texinfo.canvasX;
v[ind+1] = 1.0-(texinfo.offset + i*texinfo.skip 
- v[ind+1]*texinfo.textHeight)/texinfo.canvasY;
}
var f=new Uint16Array([
0, 1, 2, 0, 2, 3
]);
var buf21 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf21);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var ibuf21 = gl.createBuffer();
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf21);
gl.bufferData(gl.ELEMENT_ARRAY_BUFFER, f, gl.STATIC_DRAW);
var mvMatLoc21 = gl.getUniformLocation(prog21,"mvMatrix");
var prMatLoc21 = gl.getUniformLocation(prog21,"prMatrix");
// ****** text object 22 ******
var prog22  = gl.createProgram();
gl.attachShader(prog22, getShader( gl, "unnamed_chunk_2vshader22" ));
gl.attachShader(prog22, getShader( gl, "unnamed_chunk_2fshader22" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog22, 0, "aPos");
gl.bindAttribLocation(prog22, 1, "aCol");
gl.linkProgram(prog22);
var texts = [
"Axis 3"
];
var texinfo = drawTextToCanvas(texts, 1);	 
var canvasX22 = texinfo.canvasX;
var canvasY22 = texinfo.canvasY;
var ofsLoc22 = gl.getAttribLocation(prog22, "aOfs");
var texture22 = gl.createTexture();
var texLoc22 = gl.getAttribLocation(prog22, "aTexcoord");
var sampler22 = gl.getUniformLocation(prog22,"uSampler");
handleLoadedTexture(texture22, document.getElementById("unnamed_chunk_2textureCanvas"));
var v=new Float32Array([
-0.8365118, -0.98827, -0.03733748, 0, -0.5, 0.5, 0.5,
-0.8365118, -0.98827, -0.03733748, 1, -0.5, 0.5, 0.5,
-0.8365118, -0.98827, -0.03733748, 1, 1.5, 0.5, 0.5,
-0.8365118, -0.98827, -0.03733748, 0, 1.5, 0.5, 0.5
]);
for (var i=0; i<1; i++) 
for (var j=0; j<4; j++) {
ind = 7*(4*i + j) + 3;
v[ind+2] = 2*(v[ind]-v[ind+2])*texinfo.widths[i]/width;
v[ind+3] = 2*(v[ind+1]-v[ind+3])*texinfo.textHeight/height;
v[ind] *= texinfo.widths[i]/texinfo.canvasX;
v[ind+1] = 1.0-(texinfo.offset + i*texinfo.skip 
- v[ind+1]*texinfo.textHeight)/texinfo.canvasY;
}
var f=new Uint16Array([
0, 1, 2, 0, 2, 3
]);
var buf22 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf22);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var ibuf22 = gl.createBuffer();
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf22);
gl.bufferData(gl.ELEMENT_ARRAY_BUFFER, f, gl.STATIC_DRAW);
var mvMatLoc22 = gl.getUniformLocation(prog22,"mvMatrix");
var prMatLoc22 = gl.getUniformLocation(prog22,"prMatrix");
// ****** lines object 23 ******
var prog23  = gl.createProgram();
gl.attachShader(prog23, getShader( gl, "unnamed_chunk_2vshader23" ));
gl.attachShader(prog23, getShader( gl, "unnamed_chunk_2fshader23" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog23, 0, "aPos");
gl.bindAttribLocation(prog23, 1, "aCol");
gl.linkProgram(prog23);
var v=new Float32Array([
-0.6, -0.7629825, -0.7840275,
0.6, -0.7629825, -0.7840275,
-0.6, -0.7629825, -0.7840275,
-0.6, -0.8005304, -0.821362,
-0.4, -0.7629825, -0.7840275,
-0.4, -0.8005304, -0.821362,
-0.2, -0.7629825, -0.7840275,
-0.2, -0.8005304, -0.821362,
0, -0.7629825, -0.7840275,
0, -0.8005304, -0.821362,
0.2, -0.7629825, -0.7840275,
0.2, -0.8005304, -0.821362,
0.4, -0.7629825, -0.7840275,
0.4, -0.8005304, -0.821362,
0.6, -0.7629825, -0.7840275,
0.6, -0.8005304, -0.821362
]);
var buf23 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf23);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var mvMatLoc23 = gl.getUniformLocation(prog23,"mvMatrix");
var prMatLoc23 = gl.getUniformLocation(prog23,"prMatrix");
// ****** text object 24 ******
var prog24  = gl.createProgram();
gl.attachShader(prog24, getShader( gl, "unnamed_chunk_2vshader24" ));
gl.attachShader(prog24, getShader( gl, "unnamed_chunk_2fshader24" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog24, 0, "aPos");
gl.bindAttribLocation(prog24, 1, "aCol");
gl.linkProgram(prog24);
var texts = [
"-0.6",
"-0.4",
"-0.2",
"0",
"0.2",
"0.4",
"0.6"
];
var texinfo = drawTextToCanvas(texts, 1);	 
var canvasX24 = texinfo.canvasX;
var canvasY24 = texinfo.canvasY;
var ofsLoc24 = gl.getAttribLocation(prog24, "aOfs");
var texture24 = gl.createTexture();
var texLoc24 = gl.getAttribLocation(prog24, "aTexcoord");
var sampler24 = gl.getUniformLocation(prog24,"uSampler");
handleLoadedTexture(texture24, document.getElementById("unnamed_chunk_2textureCanvas"));
var v=new Float32Array([
-0.6, -0.8756263, -0.896031, 0, -0.5, 0.5, 0.5,
-0.6, -0.8756263, -0.896031, 1, -0.5, 0.5, 0.5,
-0.6, -0.8756263, -0.896031, 1, 1.5, 0.5, 0.5,
-0.6, -0.8756263, -0.896031, 0, 1.5, 0.5, 0.5,
-0.4, -0.8756263, -0.896031, 0, -0.5, 0.5, 0.5,
-0.4, -0.8756263, -0.896031, 1, -0.5, 0.5, 0.5,
-0.4, -0.8756263, -0.896031, 1, 1.5, 0.5, 0.5,
-0.4, -0.8756263, -0.896031, 0, 1.5, 0.5, 0.5,
-0.2, -0.8756263, -0.896031, 0, -0.5, 0.5, 0.5,
-0.2, -0.8756263, -0.896031, 1, -0.5, 0.5, 0.5,
-0.2, -0.8756263, -0.896031, 1, 1.5, 0.5, 0.5,
-0.2, -0.8756263, -0.896031, 0, 1.5, 0.5, 0.5,
0, -0.8756263, -0.896031, 0, -0.5, 0.5, 0.5,
0, -0.8756263, -0.896031, 1, -0.5, 0.5, 0.5,
0, -0.8756263, -0.896031, 1, 1.5, 0.5, 0.5,
0, -0.8756263, -0.896031, 0, 1.5, 0.5, 0.5,
0.2, -0.8756263, -0.896031, 0, -0.5, 0.5, 0.5,
0.2, -0.8756263, -0.896031, 1, -0.5, 0.5, 0.5,
0.2, -0.8756263, -0.896031, 1, 1.5, 0.5, 0.5,
0.2, -0.8756263, -0.896031, 0, 1.5, 0.5, 0.5,
0.4, -0.8756263, -0.896031, 0, -0.5, 0.5, 0.5,
0.4, -0.8756263, -0.896031, 1, -0.5, 0.5, 0.5,
0.4, -0.8756263, -0.896031, 1, 1.5, 0.5, 0.5,
0.4, -0.8756263, -0.896031, 0, 1.5, 0.5, 0.5,
0.6, -0.8756263, -0.896031, 0, -0.5, 0.5, 0.5,
0.6, -0.8756263, -0.896031, 1, -0.5, 0.5, 0.5,
0.6, -0.8756263, -0.896031, 1, 1.5, 0.5, 0.5,
0.6, -0.8756263, -0.896031, 0, 1.5, 0.5, 0.5
]);
for (var i=0; i<7; i++) 
for (var j=0; j<4; j++) {
ind = 7*(4*i + j) + 3;
v[ind+2] = 2*(v[ind]-v[ind+2])*texinfo.widths[i]/width;
v[ind+3] = 2*(v[ind+1]-v[ind+3])*texinfo.textHeight/height;
v[ind] *= texinfo.widths[i]/texinfo.canvasX;
v[ind+1] = 1.0-(texinfo.offset + i*texinfo.skip 
- v[ind+1]*texinfo.textHeight)/texinfo.canvasY;
}
var f=new Uint16Array([
0, 1, 2, 0, 2, 3,
4, 5, 6, 4, 6, 7,
8, 9, 10, 8, 10, 11,
12, 13, 14, 12, 14, 15,
16, 17, 18, 16, 18, 19,
20, 21, 22, 20, 22, 23,
24, 25, 26, 24, 26, 27
]);
var buf24 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf24);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var ibuf24 = gl.createBuffer();
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf24);
gl.bufferData(gl.ELEMENT_ARRAY_BUFFER, f, gl.STATIC_DRAW);
var mvMatLoc24 = gl.getUniformLocation(prog24,"mvMatrix");
var prMatLoc24 = gl.getUniformLocation(prog24,"prMatrix");
// ****** lines object 25 ******
var prog25  = gl.createProgram();
gl.attachShader(prog25, getShader( gl, "unnamed_chunk_2vshader25" ));
gl.attachShader(prog25, getShader( gl, "unnamed_chunk_2fshader25" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog25, 0, "aPos");
gl.bindAttribLocation(prog25, 1, "aCol");
gl.linkProgram(prog25);
var v=new Float32Array([
-0.6441854, -0.5, -0.7840275,
-0.6441854, 0.5, -0.7840275,
-0.6441854, -0.5, -0.7840275,
-0.6762398, -0.5, -0.821362,
-0.6441854, 0, -0.7840275,
-0.6762398, 0, -0.821362,
-0.6441854, 0.5, -0.7840275,
-0.6762398, 0.5, -0.821362
]);
var buf25 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf25);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var mvMatLoc25 = gl.getUniformLocation(prog25,"mvMatrix");
var prMatLoc25 = gl.getUniformLocation(prog25,"prMatrix");
// ****** text object 26 ******
var prog26  = gl.createProgram();
gl.attachShader(prog26, getShader( gl, "unnamed_chunk_2vshader26" ));
gl.attachShader(prog26, getShader( gl, "unnamed_chunk_2fshader26" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog26, 0, "aPos");
gl.bindAttribLocation(prog26, 1, "aCol");
gl.linkProgram(prog26);
var texts = [
"-0.5",
"0",
"0.5"
];
var texinfo = drawTextToCanvas(texts, 1);	 
var canvasX26 = texinfo.canvasX;
var canvasY26 = texinfo.canvasY;
var ofsLoc26 = gl.getAttribLocation(prog26, "aOfs");
var texture26 = gl.createTexture();
var texLoc26 = gl.getAttribLocation(prog26, "aTexcoord");
var sampler26 = gl.getUniformLocation(prog26,"uSampler");
handleLoadedTexture(texture26, document.getElementById("unnamed_chunk_2textureCanvas"));
var v=new Float32Array([
-0.7403486, -0.5, -0.896031, 0, -0.5, 0.5, 0.5,
-0.7403486, -0.5, -0.896031, 1, -0.5, 0.5, 0.5,
-0.7403486, -0.5, -0.896031, 1, 1.5, 0.5, 0.5,
-0.7403486, -0.5, -0.896031, 0, 1.5, 0.5, 0.5,
-0.7403486, 0, -0.896031, 0, -0.5, 0.5, 0.5,
-0.7403486, 0, -0.896031, 1, -0.5, 0.5, 0.5,
-0.7403486, 0, -0.896031, 1, 1.5, 0.5, 0.5,
-0.7403486, 0, -0.896031, 0, 1.5, 0.5, 0.5,
-0.7403486, 0.5, -0.896031, 0, -0.5, 0.5, 0.5,
-0.7403486, 0.5, -0.896031, 1, -0.5, 0.5, 0.5,
-0.7403486, 0.5, -0.896031, 1, 1.5, 0.5, 0.5,
-0.7403486, 0.5, -0.896031, 0, 1.5, 0.5, 0.5
]);
for (var i=0; i<3; i++) 
for (var j=0; j<4; j++) {
ind = 7*(4*i + j) + 3;
v[ind+2] = 2*(v[ind]-v[ind+2])*texinfo.widths[i]/width;
v[ind+3] = 2*(v[ind+1]-v[ind+3])*texinfo.textHeight/height;
v[ind] *= texinfo.widths[i]/texinfo.canvasX;
v[ind+1] = 1.0-(texinfo.offset + i*texinfo.skip 
- v[ind+1]*texinfo.textHeight)/texinfo.canvasY;
}
var f=new Uint16Array([
0, 1, 2, 0, 2, 3,
4, 5, 6, 4, 6, 7,
8, 9, 10, 8, 10, 11
]);
var buf26 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf26);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var ibuf26 = gl.createBuffer();
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf26);
gl.bufferData(gl.ELEMENT_ARRAY_BUFFER, f, gl.STATIC_DRAW);
var mvMatLoc26 = gl.getUniformLocation(prog26,"mvMatrix");
var prMatLoc26 = gl.getUniformLocation(prog26,"prMatrix");
// ****** lines object 27 ******
var prog27  = gl.createProgram();
gl.attachShader(prog27, getShader( gl, "unnamed_chunk_2vshader27" ));
gl.attachShader(prog27, getShader( gl, "unnamed_chunk_2fshader27" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog27, 0, "aPos");
gl.bindAttribLocation(prog27, 1, "aCol");
gl.linkProgram(prog27);
var v=new Float32Array([
-0.6441854, -0.7629825, -0.5,
-0.6441854, -0.7629825, 0.5,
-0.6441854, -0.7629825, -0.5,
-0.6762398, -0.8005304, -0.5,
-0.6441854, -0.7629825, 0,
-0.6762398, -0.8005304, 0,
-0.6441854, -0.7629825, 0.5,
-0.6762398, -0.8005304, 0.5
]);
var buf27 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf27);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var mvMatLoc27 = gl.getUniformLocation(prog27,"mvMatrix");
var prMatLoc27 = gl.getUniformLocation(prog27,"prMatrix");
// ****** text object 28 ******
var prog28  = gl.createProgram();
gl.attachShader(prog28, getShader( gl, "unnamed_chunk_2vshader28" ));
gl.attachShader(prog28, getShader( gl, "unnamed_chunk_2fshader28" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog28, 0, "aPos");
gl.bindAttribLocation(prog28, 1, "aCol");
gl.linkProgram(prog28);
var texts = [
"-0.5",
"0",
"0.5"
];
var texinfo = drawTextToCanvas(texts, 1);	 
var canvasX28 = texinfo.canvasX;
var canvasY28 = texinfo.canvasY;
var ofsLoc28 = gl.getAttribLocation(prog28, "aOfs");
var texture28 = gl.createTexture();
var texLoc28 = gl.getAttribLocation(prog28, "aTexcoord");
var sampler28 = gl.getUniformLocation(prog28,"uSampler");
handleLoadedTexture(texture28, document.getElementById("unnamed_chunk_2textureCanvas"));
var v=new Float32Array([
-0.7403486, -0.8756263, -0.5, 0, -0.5, 0.5, 0.5,
-0.7403486, -0.8756263, -0.5, 1, -0.5, 0.5, 0.5,
-0.7403486, -0.8756263, -0.5, 1, 1.5, 0.5, 0.5,
-0.7403486, -0.8756263, -0.5, 0, 1.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0, 0, -0.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0, 1, -0.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0, 1, 1.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0, 0, 1.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0.5, 0, -0.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0.5, 1, -0.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0.5, 1, 1.5, 0.5, 0.5,
-0.7403486, -0.8756263, 0.5, 0, 1.5, 0.5, 0.5
]);
for (var i=0; i<3; i++) 
for (var j=0; j<4; j++) {
ind = 7*(4*i + j) + 3;
v[ind+2] = 2*(v[ind]-v[ind+2])*texinfo.widths[i]/width;
v[ind+3] = 2*(v[ind+1]-v[ind+3])*texinfo.textHeight/height;
v[ind] *= texinfo.widths[i]/texinfo.canvasX;
v[ind+1] = 1.0-(texinfo.offset + i*texinfo.skip 
- v[ind+1]*texinfo.textHeight)/texinfo.canvasY;
}
var f=new Uint16Array([
0, 1, 2, 0, 2, 3,
4, 5, 6, 4, 6, 7,
8, 9, 10, 8, 10, 11
]);
var buf28 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf28);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var ibuf28 = gl.createBuffer();
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf28);
gl.bufferData(gl.ELEMENT_ARRAY_BUFFER, f, gl.STATIC_DRAW);
var mvMatLoc28 = gl.getUniformLocation(prog28,"mvMatrix");
var prMatLoc28 = gl.getUniformLocation(prog28,"prMatrix");
// ****** lines object 29 ******
var prog29  = gl.createProgram();
gl.attachShader(prog29, getShader( gl, "unnamed_chunk_2vshader29" ));
gl.attachShader(prog29, getShader( gl, "unnamed_chunk_2fshader29" ));
//  Force aPos to location 0, aCol to location 1 
gl.bindAttribLocation(prog29, 0, "aPos");
gl.bindAttribLocation(prog29, 1, "aCol");
gl.linkProgram(prog29);
var v=new Float32Array([
-0.6441854, -0.7629825, -0.7840275,
-0.6441854, 0.7389345, -0.7840275,
-0.6441854, -0.7629825, 0.7093525,
-0.6441854, 0.7389345, 0.7093525,
-0.6441854, -0.7629825, -0.7840275,
-0.6441854, -0.7629825, 0.7093525,
-0.6441854, 0.7389345, -0.7840275,
-0.6441854, 0.7389345, 0.7093525,
-0.6441854, -0.7629825, -0.7840275,
0.6379904, -0.7629825, -0.7840275,
-0.6441854, -0.7629825, 0.7093525,
0.6379904, -0.7629825, 0.7093525,
-0.6441854, 0.7389345, -0.7840275,
0.6379904, 0.7389345, -0.7840275,
-0.6441854, 0.7389345, 0.7093525,
0.6379904, 0.7389345, 0.7093525,
0.6379904, -0.7629825, -0.7840275,
0.6379904, 0.7389345, -0.7840275,
0.6379904, -0.7629825, 0.7093525,
0.6379904, 0.7389345, 0.7093525,
0.6379904, -0.7629825, -0.7840275,
0.6379904, -0.7629825, 0.7093525,
0.6379904, 0.7389345, -0.7840275,
0.6379904, 0.7389345, 0.7093525
]);
var buf29 = gl.createBuffer();
gl.bindBuffer(gl.ARRAY_BUFFER, buf29);
gl.bufferData(gl.ARRAY_BUFFER, v, gl.STATIC_DRAW);
var mvMatLoc29 = gl.getUniformLocation(prog29,"mvMatrix");
var prMatLoc29 = gl.getUniformLocation(prog29,"prMatrix");
gl.enable(gl.DEPTH_TEST);
gl.depthFunc(gl.LEQUAL);
gl.clearDepth(1.0);
gl.clearColor(1, 1, 1, 1);
var xOffs = yOffs = 0,  drag  = 0;
drawScene();
function drawScene(){
gl.depthMask(true);
gl.disable(gl.BLEND);
var radius = 1.322064;
var s = sin(fov*PI/360);
var t = tan(fov*PI/360);
var distance = radius/s;
var near = distance - radius;
var far = distance + radius;
var hlen = t*near;
var aspect = width/height;
prMatrix.makeIdentity();
if (aspect > 1)
prMatrix.frustum(-hlen*aspect*zoom, hlen*aspect*zoom, 
-hlen*zoom, hlen*zoom, near, far);
else  
prMatrix.frustum(-hlen*zoom, hlen*zoom, 
-hlen*zoom/aspect, hlen*zoom/aspect, 
near, far);
mvMatrix.makeIdentity();
mvMatrix.translate( 0.003097504, 0.01202399, 0.03733748 );
mvMatrix.scale( 1.114856, 0.951745, 0.9571857 );   
mvMatrix.multRight( userMatrix );  
mvMatrix.translate(0, 0, -distance);
normMatrix.makeIdentity();
normMatrix.scale( 0.8969764, 1.050702, 1.044729 );   
normMatrix.multRight( userMatrix );
gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);
// ****** spheres object 18 *******
gl.useProgram(prog18);
gl.bindBuffer(gl.ARRAY_BUFFER, sphereBuf);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, sphereIbuf);
gl.uniformMatrix4fv( prMatLoc18, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc18, false, new Float32Array(mvMatrix.getAsArray()) );
gl.uniformMatrix4fv( normMatLoc18, false, new Float32Array(normMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 12,  0);
gl.enableVertexAttribArray(normLoc18 );
gl.vertexAttribPointer(normLoc18,  3, gl.FLOAT, false, 12,  0);
gl.disableVertexAttribArray( colLoc );
var sphereNorm = new CanvasMatrix4();
sphereNorm.scale(1.114856, 0.951745, 0.9571857);
sphereNorm.multRight(normMatrix);
gl.uniformMatrix4fv( normMatLoc18, false, new Float32Array(sphereNorm.getAsArray()) );
for (var i = 0; i < 111; i++) {
var sphereMV = new CanvasMatrix4();
var baseofs = i*8
var ofs = baseofs + 7;	       
var scale = values18[ofs];
sphereMV.scale(0.8969764*scale, 1.050702*scale, 1.044729*scale);
sphereMV.translate(values18[baseofs], 
values18[baseofs+1], 
values18[baseofs+2]);
sphereMV.multRight(mvMatrix);
gl.uniformMatrix4fv( mvMatLoc18, false, new Float32Array(sphereMV.getAsArray()) );
ofs = baseofs + 3;       
gl.vertexAttrib4f( colLoc, values18[ofs], 
values18[ofs+1], 
values18[ofs+2],
values18[ofs+3] );
gl.drawElements(gl.TRIANGLES, 384, gl.UNSIGNED_SHORT, 0);
}
// ****** text object 20 *******
gl.useProgram(prog20);
gl.bindBuffer(gl.ARRAY_BUFFER, buf20);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf20);
gl.uniformMatrix4fv( prMatLoc20, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc20, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.enableVertexAttribArray( texLoc20 );
gl.vertexAttribPointer(texLoc20, 2, gl.FLOAT, false, 28, 12);
gl.activeTexture(gl.TEXTURE0);
gl.bindTexture(gl.TEXTURE_2D, texture20);
gl.uniform1i( sampler20, 0);
gl.enableVertexAttribArray( ofsLoc20 );
gl.vertexAttribPointer(ofsLoc20, 2, gl.FLOAT, false, 28, 20);
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 28,  0);
gl.drawElements(gl.TRIANGLES, 6, gl.UNSIGNED_SHORT, 0);
// ****** text object 21 *******
gl.useProgram(prog21);
gl.bindBuffer(gl.ARRAY_BUFFER, buf21);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf21);
gl.uniformMatrix4fv( prMatLoc21, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc21, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.enableVertexAttribArray( texLoc21 );
gl.vertexAttribPointer(texLoc21, 2, gl.FLOAT, false, 28, 12);
gl.activeTexture(gl.TEXTURE0);
gl.bindTexture(gl.TEXTURE_2D, texture21);
gl.uniform1i( sampler21, 0);
gl.enableVertexAttribArray( ofsLoc21 );
gl.vertexAttribPointer(ofsLoc21, 2, gl.FLOAT, false, 28, 20);
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 28,  0);
gl.drawElements(gl.TRIANGLES, 6, gl.UNSIGNED_SHORT, 0);
// ****** text object 22 *******
gl.useProgram(prog22);
gl.bindBuffer(gl.ARRAY_BUFFER, buf22);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf22);
gl.uniformMatrix4fv( prMatLoc22, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc22, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.enableVertexAttribArray( texLoc22 );
gl.vertexAttribPointer(texLoc22, 2, gl.FLOAT, false, 28, 12);
gl.activeTexture(gl.TEXTURE0);
gl.bindTexture(gl.TEXTURE_2D, texture22);
gl.uniform1i( sampler22, 0);
gl.enableVertexAttribArray( ofsLoc22 );
gl.vertexAttribPointer(ofsLoc22, 2, gl.FLOAT, false, 28, 20);
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 28,  0);
gl.drawElements(gl.TRIANGLES, 6, gl.UNSIGNED_SHORT, 0);
// ****** lines object 23 *******
gl.useProgram(prog23);
gl.bindBuffer(gl.ARRAY_BUFFER, buf23);
gl.uniformMatrix4fv( prMatLoc23, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc23, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.lineWidth( 1 );
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 12,  0);
gl.drawArrays(gl.LINES, 0, 16);
// ****** text object 24 *******
gl.useProgram(prog24);
gl.bindBuffer(gl.ARRAY_BUFFER, buf24);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf24);
gl.uniformMatrix4fv( prMatLoc24, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc24, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.enableVertexAttribArray( texLoc24 );
gl.vertexAttribPointer(texLoc24, 2, gl.FLOAT, false, 28, 12);
gl.activeTexture(gl.TEXTURE0);
gl.bindTexture(gl.TEXTURE_2D, texture24);
gl.uniform1i( sampler24, 0);
gl.enableVertexAttribArray( ofsLoc24 );
gl.vertexAttribPointer(ofsLoc24, 2, gl.FLOAT, false, 28, 20);
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 28,  0);
gl.drawElements(gl.TRIANGLES, 42, gl.UNSIGNED_SHORT, 0);
// ****** lines object 25 *******
gl.useProgram(prog25);
gl.bindBuffer(gl.ARRAY_BUFFER, buf25);
gl.uniformMatrix4fv( prMatLoc25, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc25, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.lineWidth( 1 );
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 12,  0);
gl.drawArrays(gl.LINES, 0, 8);
// ****** text object 26 *******
gl.useProgram(prog26);
gl.bindBuffer(gl.ARRAY_BUFFER, buf26);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf26);
gl.uniformMatrix4fv( prMatLoc26, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc26, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.enableVertexAttribArray( texLoc26 );
gl.vertexAttribPointer(texLoc26, 2, gl.FLOAT, false, 28, 12);
gl.activeTexture(gl.TEXTURE0);
gl.bindTexture(gl.TEXTURE_2D, texture26);
gl.uniform1i( sampler26, 0);
gl.enableVertexAttribArray( ofsLoc26 );
gl.vertexAttribPointer(ofsLoc26, 2, gl.FLOAT, false, 28, 20);
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 28,  0);
gl.drawElements(gl.TRIANGLES, 18, gl.UNSIGNED_SHORT, 0);
// ****** lines object 27 *******
gl.useProgram(prog27);
gl.bindBuffer(gl.ARRAY_BUFFER, buf27);
gl.uniformMatrix4fv( prMatLoc27, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc27, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.lineWidth( 1 );
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 12,  0);
gl.drawArrays(gl.LINES, 0, 8);
// ****** text object 28 *******
gl.useProgram(prog28);
gl.bindBuffer(gl.ARRAY_BUFFER, buf28);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, ibuf28);
gl.uniformMatrix4fv( prMatLoc28, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc28, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.enableVertexAttribArray( texLoc28 );
gl.vertexAttribPointer(texLoc28, 2, gl.FLOAT, false, 28, 12);
gl.activeTexture(gl.TEXTURE0);
gl.bindTexture(gl.TEXTURE_2D, texture28);
gl.uniform1i( sampler28, 0);
gl.enableVertexAttribArray( ofsLoc28 );
gl.vertexAttribPointer(ofsLoc28, 2, gl.FLOAT, false, 28, 20);
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 28,  0);
gl.drawElements(gl.TRIANGLES, 18, gl.UNSIGNED_SHORT, 0);
// ****** lines object 29 *******
gl.useProgram(prog29);
gl.bindBuffer(gl.ARRAY_BUFFER, buf29);
gl.uniformMatrix4fv( prMatLoc29, false, new Float32Array(prMatrix.getAsArray()) );
gl.uniformMatrix4fv( mvMatLoc29, false, new Float32Array(mvMatrix.getAsArray()) );
gl.enableVertexAttribArray( posLoc );
gl.disableVertexAttribArray( colLoc );
gl.vertexAttrib4f( colLoc, 0, 0, 0, 1 );
gl.lineWidth( 1 );
gl.vertexAttribPointer(posLoc,  3, gl.FLOAT, false, 12,  0);
gl.drawArrays(gl.LINES, 0, 24);
gl.flush ();
}
var vlen = function(v) {
return sqrt(v[0]*v[0] + v[1]*v[1] + v[2]*v[2])
}
var xprod = function(a, b) {
return [a[1]*b[2] - a[2]*b[1],
a[2]*b[0] - a[0]*b[2],
a[0]*b[1] - a[1]*b[0]];
}
var screenToVector = function(x, y) {
var radius = max(width, height)/2.0;
var cx = width/2.0;
var cy = height/2.0;
var px = (x-cx)/radius;
var py = (y-cy)/radius;
var plen = sqrt(px*px+py*py);
if (plen > 1.e-6) { 
px = px/plen;
py = py/plen;
}
var angle = (SQRT2 - plen)/SQRT2*PI/2;
var z = sin(angle);
var zlen = sqrt(1.0 - z*z);
px = px * zlen;
py = py * zlen;
return [px, py, z];
}
var rotBase;
var trackballdown = function(x,y) {
rotBase = screenToVector(x, y);
saveMat.load(userMatrix);
}
var trackballmove = function(x,y) {
var rotCurrent = screenToVector(x,y);
var dot = rotBase[0]*rotCurrent[0] + 
rotBase[1]*rotCurrent[1] + 
rotBase[2]*rotCurrent[2];
var angle = acos( dot/vlen(rotBase)/vlen(rotCurrent) )*180./PI;
var axis = xprod(rotBase, rotCurrent);
userMatrix.load(saveMat);
userMatrix.rotate(angle, axis[0], axis[1], axis[2]);
drawScene();
}
var y0zoom = 0;
var zoom0 = 1;
var zoomdown = function(x, y) {
y0zoom = y;
zoom0 = log(zoom);
}
var zoommove = function(x, y) {
zoom = exp(zoom0 + (y-y0zoom)/height);
drawScene();
}
var y0fov = 0;
var fov0 = 1;
var fovdown = function(x, y) {
y0fov = y;
fov0 = fov;
}
var fovmove = function(x, y) {
fov = max(1, min(179, fov0 + 180*(y-y0fov)/height));
drawScene();
}
var mousedown = [trackballdown, zoomdown, fovdown];
var mousemove = [trackballmove, zoommove, fovmove];
function relMouseCoords(event){
var totalOffsetX = 0;
var totalOffsetY = 0;
var currentElement = canvas;
do{
totalOffsetX += currentElement.offsetLeft;
totalOffsetY += currentElement.offsetTop;
}
while(currentElement = currentElement.offsetParent)
var canvasX = event.pageX - totalOffsetX;
var canvasY = event.pageY - totalOffsetY;
return {x:canvasX, y:canvasY}
}
canvas.onmousedown = function ( ev ){
if (!ev.which) // Use w3c defns in preference to MS
switch (ev.button) {
case 0: ev.which = 1; break;
case 1: 
case 4: ev.which = 2; break;
case 2: ev.which = 3;
}
drag = ev.which;
var f = mousedown[drag-1];
if (f) {
var coords = relMouseCoords(ev);
f(coords.x, height-coords.y); 
ev.preventDefault();
}
}    
canvas.onmouseup = function ( ev ){	
drag = 0;
}
canvas.onmouseout = canvas.onmouseup;
canvas.onmousemove = function ( ev ){
if ( drag == 0 ) return;
var f = mousemove[drag-1];
if (f) {
var coords = relMouseCoords(ev);
f(coords.x, height-coords.y);
}
}
var wheelHandler = function(ev) {
var del = 1.1;
if (ev.shiftKey) del = 1.01;
var ds = ((ev.detail || ev.wheelDelta) > 0) ? del : (1 / del);
zoom *= ds;
drawScene();
ev.preventDefault();
};
canvas.addEventListener("DOMMouseScroll", wheelHandler, false);
canvas.addEventListener("mousewheel", wheelHandler, false);
}
</script>
<canvas id="unnamed_chunk_2canvas" width="1" height="1"></canvas> 
<p id="unnamed_chunk_2debug">
You must enable Javascript to view this page properly.</p>
<script>unnamed_chunk_2webGLStart();</script>

--- &twocol

## Germ-free transplant models  

***{name: left}
* Crazy transplants
  * Zebrafish -> Mouse
  * Mouse -> Zebrafish
  * Host manipulates the community to look more like itself
* Even crazier (2014)
  * Soil -> Mouse
  * Termite -> Mouse
  * Zebrafish -> Mouse


***{name: right}

<img src="http://origin-ars.els-cdn.com/content/image/1-s2.0-S0092867406012268-gr2.jpg" style="margin:0px auto;display:block" width="300">

# Rawls et al. (2006) Cell 127:434

---

## Slightly less bizarre: mouse into mouse

<img src="assets/fig/unnamed-chunk-3-1.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />

# Marino et al. (2014) PNAS

--- &twocol

## Slightly less bizarre: mouse into mouse

***{name: left}
* Communities did not resemble the innoculum (cecum)
* Initially a lot of variation between individuals
* Over time inter-individual variation calmed down
* Communities stabilized



***{name: right}
<img src="assets/fig/unnamed-chunk-4-1.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" style="display: block; margin: auto;" />

# Marino et al. (2014) PNAS

---

## Can we humanize mice?

> "16S rRNA surveys of gut samples obtained from mice in both diet groups
> revealed that engraftment of the human gut microbiota was largely successful:
> All bacterial phyla, 11 of 12 bacterial classes, and 88% (58 of 66) of
> genus-level taxa detected in the donor sample were detected among the recipient
> mice"

# Turnbaugh et al. (2009) Sci. Transl. Med

---

## Intriguing insights

* Humans are a pain
* Unable to differentiate between the microbiota of animals living in a
similar environment and consuming a similar diet
* The similarity of community structure between co-housed germ free mice
colonized with murine cecal contents increases over time
* The ability to colonize germ-free mice with diverse microbiota is an
attractive method for studying community assembly

--- .segue .dark

## Studying community assembly in germ-free mice

---

## Questions...

1. How well do germ-free mice resemble their human donors?
2. Does intra-individual variation stabilize with time?
3. Does inter-individual variation, within a cage, stabilize with time?
4. How reproducible is community assembly across cages when using the same donor?
5. How important is host genetics in shaping community struture?
6. Are the "climax" communities more similar to each other than the donors were
to each other?

--- &vcenter

*And they said you can't do hypothesis-driven microbial ecology research ...*

---

## Experimental strategy

* Colonize germ-free mice with feces from 11 human donors
  * 3-5 mice per cage
  * 1-4 cages per donor
* Obtain stool samples for ~20 days
* Sequenced the V4 region of the 16S rRNA gene on a MiSeq using Kozich et al.
(2013) protocol
  * Error rate of ~0.01%
  * Data analyzed in mothur

---

## Considerable biodiversity among donors

<img src="assets/fig/unnamed-chunk-5-1.png" title="plot of chunk unnamed-chunk-5" alt="plot of chunk unnamed-chunk-5" style="display: block; margin: auto;" />

---

## Considerable biodiversity among donors

<img src="assets/fig/unnamed-chunk-6-1.png" title="plot of chunk unnamed-chunk-6" alt="plot of chunk unnamed-chunk-6" style="display: block; margin: auto;" />

---

## How well do germ-free mice resemble their human donors?

<img src="assets/fig/unnamed-chunk-7-1.png" title="plot of chunk unnamed-chunk-7" alt="plot of chunk unnamed-chunk-7" style="display: block; margin: auto;" />


---

## Does intra-individual variation stabilize with time?


<img src="assets/fig/unnamed-chunk-8-1.png" title="plot of chunk unnamed-chunk-8" alt="plot of chunk unnamed-chunk-8" style="display: block; margin: auto;" />

---

## Does inter-individual variation, within a cage, stabilize with time?

<img src="assets/fig/unnamed-chunk-9-1.png" title="plot of chunk unnamed-chunk-9" alt="plot of chunk unnamed-chunk-9" style="display: block; margin: auto;" />


---

## How reproducible is community assembly across cages when using the same donor?

<img src="assets/fig/unnamed-chunk-10-1.png" title="plot of chunk unnamed-chunk-10" alt="plot of chunk unnamed-chunk-10" style="display: block; margin: auto;" />

--- &twocol

## How important is host genetics in shaping community struture?

***{name: left}

<img src="http://www.taconic.com/cs/Satellite?blobcol=urlimage&blobkey=id&blobtable=TA_Media&blobwhere=1347215404642&ssbinary=true" style="margin:0px auto;display:block" width="500">

***{name: right}

<img src="http://www.taconic.com/cs/Satellite?blobcol=urlimage&blobkey=id&blobtable=TA_Media&blobwhere=1347215377603&ssbinary=true" style="margin:0px auto;display:block" width="500">

---

## How important is host genetics in shaping community struture?


<img src="assets/fig/unnamed-chunk-11-1.png" title="plot of chunk unnamed-chunk-11" alt="plot of chunk unnamed-chunk-11" style="display: block; margin: auto;" />

---

## Are the "climax" communities more similar to each other than the donors were to each other?

<img src="assets/fig/unnamed-chunk-12-1.png" title="plot of chunk unnamed-chunk-12" alt="plot of chunk unnamed-chunk-12" style="display: block; margin: auto;" />

---

## Are the "climax" communities more similar to each other than the donors were to each other?


---

## Answers...
1. How well do germ-free mice resemble their human donors? **Not so much**
2. Does intra-individual variation stabilize with time? **Yes**
3. Does inter-individual variation, within a cage, stabilize with time? **Yes**
4. How reproducible is community assembly across cages when using the same donor? **Very**
5. How important is host genetics in shaping community struture? **In this case, not so much**
6. Are the "climax" communities more similar to each other than the donors were
to each other? **Uh, actually the opposite**

---

## Going forward...

* Have replicated C57Bl/6 vs. Swiss Webster experiment with an additional stool sample
* Would be interesting to know how different the immune profile is for these various "climax" communities
* Think... different.

---

>* “…it would appear to be a pointless and doubtful exercise to examine and disentangle the apparently random appearing bacteria in normal feces and the intestinal tract, a situation that seems controlled by a thousand coincidences.”
>* “Yet I have nevertheless devoted myself now for a year virtually exclusively to this special study, it was with the conviction that the accurate knowledge of these conditions is essential, for the understanding of not only the physiology of digestion…, but also the pathology  and therapy of microbial intestinal diseases.”
>* Theodore Escherich, 1885

---

## Neonate gut
<img src="http://www.plosbiology.org/article/fetchObject.action?uri=info:doi/10.1371/journal.pbio.0050177.g007&representation=PNG_M" style="margin:0px auto;display:block" width="500">

#  Palmer et al. (2007) PLoS Biology

---

## A pedantic note about process...

* This presentation was prepared in R using the `knitr` and `slidify` packages.
  * It is available through our [github repository](https://github.com/pschloss/pschloss.github.io/tree/master/talks)
  * Once the manuscript is submitted the document (and paper) will be fully executable
  * `write.paper` is a reality
* If a first year grad student downloaded your sequence data from your last paper, would they be able to reproduce your results? Here are some examples from our lab:
  * [Wild *Peromyscus* paper](https://github.com/schlossLab/wild_mice)
  * [Human community type paper](http://nbviewer.ipython.org/gist/pschloss/9815766/notebook.ipynb)

--- &twocol

## Acknowledgements

***{name: left}
* Schloss Lab
  * Matt Jenior
  * JT McCrone
  * Niel Baxter
  * Alyx Schubert
  * Joe Zackular, PhD
  * Kathryn Iverson
  * Sarah Westcott


# http://goo.gl/VpSm5u

***{name: right}
* Collaborators
  * Vince Young
  * Tom Schmidt

* U of M Host-Microbiome Initiative
* Funding from NIH: R01HG005975, R01GM099514, U19AI090871, P30DK034933
