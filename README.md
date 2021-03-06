# akamai-edgeworkers-gettingstarted

## 1. before you begin

+ install akamai CLI and edgeworker cli
```
brew install akamai
akamai install edgeworkers
```
+ get your .edgerc saved on your home directory
+ add the section name of .edgerc in edgercsection in package.json
+ downlaod typescript-rollup project to your working directory


## 2. install package & etner your edgeworker info

you need to know your edgeworker name and property host name.

~~~
 yarn start

 ### (1/6) Install packages
 ### (2/6) Your EdgeWorker code name? : 
 ### (3/6) Description? : 
 ### (4/6) Set initial script version (default:0.0.1) : 
 ### (5/6) Property name associated with this ew code  : 
 ### (6/6) Host name associated with this ew code  : 
~~~

if you already have edgeworker id on portal
~~~
 yarn get-ewid
~~~
this will update ewid in package.json

## 3, create & start sandbox
change sandboxproperty in the package.json file. you can specify the Sandbox name.

~~~
 yarn new-sandbox-p
 yarn start-sandbox
~~~

## 4, do some code change
 change ./src/main.ts


## 5, update sandbox
~~~
  yarn update
~~~
this will compile your code and bundle requred package into simgle ./dist/bundle.tgz
and upload it to sandbox.


## 6, get your debug token updated
~~~
  yarn token
~~~


## 7, test your edgeworker code on Sandbox
~~~
  yarn test http://localhost:9550/path/
~~~

if code is not working, go back to #4.

## 8, if its working ok deploy it to staging & production
~~~
  yarn deploy
~~~

The above commmand will run the following:
~~~
  yarn build
  yarn upload
  yarn staging
  yarn production
~~~

## 9, test it on staging or production
~~~
  yarn test https://yourdomain.com/edgeworker_path
~~~

