---
title: "Sync & Async"
date: 2020-03-05 00:00:00 -0400
categories: jekyll update
---

### Sync & Async

- 동기 방식

  파일의 소유권을 바꾸고, 파일명을 변경, 심볼릭 링크를 만드는 작업을 순차적으로 진행.

      var fs = require('fs');

      var oldFilename = './processId.txt';
      var newFilename = './processIdOld.txt';

      fs.chmodSync(oldFilename, 777);
      console.log('complete chmod.');
      fs.renameSync(oldFilename, newFilename);
      console.log('complete rename.');
      var isSymLink = fs.lstatSync(newFilename).isSymbolicLink();
      console.log('complete symbolic check.');
      var fs = require('fs');

      var oldFilename = './processId.txt';
      var newFilename = './processIdOld.txt';

      fs.chmod(oldFilename, 777, function (err) {
          console.log('complete chmod.');
          fs.rename(oldFilename, newFilename, function (err) {
              console.log('complete rename.');
              fs.lstat(newFilename, function (err, stats) {
                  var isSymLink = stats.isSymbolicLink();
                  console.log('complete symbolic check.');
              });
          });
      });

      c:\_dev\_nodejs\nodejs1>node sync-async.js
      complete chmod.
      complete rename.
      complete symbolic check.
      complete chmod.
      complete rename.
      complete symbolic check.

- 비동기 방식

  비동기 방식에서 순차처리는 중첩된 Callback을 이용하여 순서가 보장되게 한다.

  'async' 모듈을 사용하려면 NPM으로 모듈을 설치해야 한다.

    npm install async
    
Waterfall API를 사용

    var fs = require('fs');
    var async = require('async');

    var oldFilename = './processId.txt';
    var newFilename = './processIdOld.txt';

    async.waterfall([
        function (cb) {
            fs.chmod(oldFilename, 777, function (err){
                console.log('complete chmod.');
                cb(null);
            });
        },
        function (cb) {
            fs.rename(oldFilename, newFilename, function (err) {
                console.log('complete rename.');
                cb(null);
            });
        },
        function (cb) {
            fs.lstat(newFilename, function (err, stats) {
                var isSymLink = stats.isSymbolicLink();
                console.log('complete symbolic check.');
            });
        }
    ]);

    c:\_dev\_nodejs\nodejs1>node sync-async.js
    complete chmod.
    complete rename.
    complete symbolic check.

ref http://www.nextree.co.kr/p7292/
