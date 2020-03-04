---
title: --save 와 --save-dev 
tags: npm npm-install dependencies devDependencies
---

### --save

> plugin이 ./node_modules에 설치되고 package.json 내의 *dependencies*에 추가된다.<br> 
*--production* 빌드시 해당 plugin이 **포함되지 않는다**.

### --save-dev

> plugin이 ./node_modules에 설치되고 package.json 내의 *decDependencies*에 추가된다.<br> 
*--production* 빌드시 해당 plugin이 **포함되지 않는다**.

