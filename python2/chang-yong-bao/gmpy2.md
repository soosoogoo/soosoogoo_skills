#### 问题1:

> xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun



### 解决方式

```shell
xcode-select –install
```



参考文章:<https://www.jianshu.com/p/50b6771eb853>



#### 问题2



> src/gmpy.h:252:12: fatal error: 'mpfr.h' file not found



### 解决方式

```shell
brew install libmpc mpfr gmp
```





参考文章:

<https://github.com/OpenMined/PySyft/issues/125>

<https://github.com/iamtrask/PySonar/blob/master/README.md#base-libraries>




http://docs.peewee-orm.com/en/latest/peewee/quickstart.html#quickstart