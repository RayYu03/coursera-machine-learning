# coursera-machine-learning


## 使用 `Octave 4.0` 提交时提示`HTTP response code said error`错误的[解决方法](https://learner.coursera.help/hc/en-us/community/posts/204693179-linear-regression-submit-error):



You can get it fixed by replacing
```
str=[str str0(pos0(i)+1:pos(i)-1) sprintf('_0x%X_',str0(pos(i)))];	% (1)
```
by
```
str=[str str0(pos0(i)+1:pos(i)-1) sprintf('_0x%X_',toascii(str0(pos(i))))];
```
and
```
str=sprintf('x0x%X_%s',char(str(1)),str(2:end));	% (2)
```
by
```
str=sprintf('x0x%X_%s',toascii(str(1)),str(2:end));
```

in every files that contains `(1)` or `(2)`
