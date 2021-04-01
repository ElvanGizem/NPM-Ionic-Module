   # NPM Kullanarak Ionic Modülün Yayınlanması
   
**NPM Nedir?**

 Node Package Manager, açık kaynaklı  Node.js için paket yöneticisidir  ve komut satırı üzerinden çalışır. Front-end web uygulamaları, mobil uygulamalar, robotlar, yönlendiriciler ve JavaScript kod paketleri için genel bir depodur . Bağımlılıkları yönetir ve bu bağımlılıklar package.json’da tanımlanır. Kendi modülünüzü paylaşmak istiyorsanız npm’in kendi sitesinde oturum açmanız yeterlidir.
 
 ---
**Npm Nasıl Kurulur?**

 Npm yükleyebilmek için  [https://nodejs.org/en/](https://nodejs.org/en/) sitesinden node.js kurulumunu gerçekleştirdiğinizde npm de otomatik olarak yüklenmiş olur.
 
Nodejs yüklendiğini kontrol etmek için komut satırına `$node -v`  yazabilirsiniz.

Npm kurulumunu kontrol etmek için komut satırına `$npm -v` yazabilirsiniz.




## Başlarken

Modülümüzü oluşturmak için masaüstünde bir klasör oluşturmamız gerekiyor.
Klasör oluşturmak için sırasıyla uygulanması gerekenler ;

Windows kullanıyorsanız eğer cmd'yi yönetici olarak çalıştırın ,

MAC/Linux kullanıyorsanız terminalde `$sudo` kullanarak çalıştırın.

   Windows için;

   `$cd desktop`
   
   `$mkdir diginova`
   
   
   MAC için;
   
   `$cd ~/Desktop`
   
   `$mkdir diginova`
   
  
  komutlarını çalıştırdığınızda klasör masaüstünde oluşturulacaktır.
 
 ### 2-VsCode Kullanarak Modülün Oluşturulması
Oluşturduğumuz diginova klasörünü Visual Studio Code ile açıyoruz. Visual Studio Code Linux, Mac OS ve Windows işletim sistemlerinde çalışan IDE ortamıdır.  Proje klasöründe paketleri kullanmak için bir tane package.json dosyası oluşturuyoruz.Package json içeriği aşağıdaki gibidir. 

###### 1.Adım

Bu metaveriler üzerinden projeyi tanımlamış oluyoruz.

Windows kullananlar `"build": "del -rf dist && npm run ngc",` bu şekilde build yapmalı.

MAC/Linux kullananlar  `"build": "rm -rf dist && npm run ngc"` bu şekilde build yapmalı.

###### Package.json

```{
  "name": "my_portalium-package",
  "version": "1.0.3",
  "description": "Bu benim ilk test modulum",
  "main": "./dist/index.js",
  "typings": "./dist/index.d.ts",
  "files": [
    "dist"
  ],
  "scripts": {
    "ngc": "ngc",
    "build": "del -rf dist && npm run ngc",
    "publishPackage": "npm run build && npm publish"
  },
  "repository": {
    "type": "git",
    "url": "git+"
  },
  "keywords": [],
  "author": "",
  "license": "MIT",
  "homepage": "",
  "bugs": {
    "url": ""
  },
  "devDependencies": {
    "@angular/common": "^5.0.3",
    "@angular/compiler": "^5.0.3",
    "@angular/compiler-cli": "^5.0.3",
    "@angular/core": "^5.2.11",
    "@angular/forms": "^5.2.11",
    "@angular/platform-browser": "^5.0.3",
    "@angular/platform-browser-dynamic": "^5.0.3",
    "ionic-angular": "^3.9.2",
    "rxjs": "^5.5.2",
    "typescript": "^2.4.2",
    "zone.js": "^0.8.18"
  }
}
```
###### 2.Adım

TypeScript derleyicimize projemiz hakkında bilgi vermek için bir tsconfig.json dosyası oluşturuyoruz.

###### tsconfig.json

```
{
    "compilerOptions": {
        "module": "es2015",
        "target": "es5",
        "moduleResolution": "node",
        "sourceMap": true,
        "inlineSources": true,
        "declaration": true,
        "noImplicitAny": false,
        "experimentalDecorators": true,
        "lib": ["dom", "es2015"],
        "outDir": "dist"
    },
    "exclude": [
        "node_modules",
        "dist",
        "scripts"
    ],
    "angularCompilerOptions": {
        "skipTemplateCodegen": true
    }
    }
```

VsCode'da new terminalden yeni bir komut satırı açtıktan sonra  `npm install ` komutunu çalıştırıp projemize modülü yüklüyoruz. Node_module klasörüne package.json içerisine eklediğiniz paketler kurulacaktır.

Ardından..
VsCode editörümüzde bir src klasörü oluşturuyoruz.
Kütüphane hakkındaki bilgilere devam etmeden önce kütüphaneyi kullanan ionic uygulamasını oluşturuyoruz.

###### İonic uygulamasının oluşturulması 

Proje için öncelikle masaüstünde bir klasör oluşturuyoruz.

   Windows için;

   `$cd desktop`
   
   `$mkdir ionic`
   
   MAC için;
   
   `$cd ~/Desktop`
   
   `$mkdir diginova`
   
   
   klasörümüzü oluşturduktan sonra komut satırına bu kodları yazmalıyız.
   
`ionic start devdacticLibraryApp blank --type=angular --capacitor`

`cd ./devdacticLibraryApp`

`npm link devdactic-lib`
