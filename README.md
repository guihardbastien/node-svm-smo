# node-svm-smo

[![Build Status](https://travis-ci.org/guihardbastien/node-svm-smo.svg?branch=master)](https://travis-ci.org/guihardbastien/node-svm-smo)
[![Coverage Status](https://coveralls.io/repos/github/guihardbastien/node-svm-smo/badge.svg)](https://coveralls.io/github/guihardbastien/node-svm-smo)
[![npm version](https://badge.fury.io/js/node-svm-smo.svg)](https://badge.fury.io/js/node-svm-smo)

Support Vector Machine implementing Sequential Minimal Optimisation algorithm for Node.js

## Installation

`npm i node-svm-smo`

## Basic usage

import the module : `import SVM from "node-svm-smo";`

### Example

```js
import SVM from "node-svm-smo";

const data = [
  [63.94467417052296,81.0217272621887],
  [54.87300013454443,60.84061766333669],
  [45.52048694403639,81.12464276459878],
  [48.965524328511705,57.18776467921587],
  [74.52679297504449,83.83083375121797],
  [54.37811765569671,56.03892121990233],
  [44.26860038064747,19.667730330959163],
  [49.174828952241675,45.63294964476442],
  [68.38409733522553,71.71723595963316],
  [59.78161085912989,61.55507106057365],
  [6.6500878665167775,39.49294636329541],
  [44.48056808348252,48.662212578138195]
];

const labels = [-1,1,-1,1,-1,1,-1,1,-1,1,-1,1];

const C = 5;
const kernel = 'RBF';
const RBFSigma = 15;

const MySVM = new SVM(data,labels,C,kernel,RBFSigma);

MySVM.predict([50,50]);
// expected output : 1
```

check out https://github.com/guihardbastien/Support-Vector-Machine for data visualisation.

### Parameters

-   `data` : Array of feature vectors should be of form :

`const data = [[X1,Y1,...,Z1],[X2,Y2,...,Z2],...,[Xx,Yx,...,Zx]]`

-   `labels`: Single array of data output, should match data.length

-   `C` : soft margin parameter

-   `kernel` : kernel used for the the kernel trick
    -   `RBF`: Radial Basis Function

### Options

-   `RBFSigma`:

### Methods

-   `predict(data)` : returns binary classification of an input

## TO DO

-   [ ] Add default parameters
-   [ ] Add more kernels
-   [ ] Write tests
-   [ ] Comment code :trollface:

## Sources

-   https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-98-14.pdf
-   http://cs229.stanford.edu/materials/smo.pdf

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
