### Jenkins的xUnit解析错误与问题解决

现象: xUnit不能解析脚本生成的xml格式报告，Jenkins版本为Jenkins2.121.1，而相同的测试报告在版本为Jenkins2.107.3的Jenkins环境中能正常被解析

日志:

```
16:19:37 WARNING: The file 'D:\Jenkins\workspace\Balboa_Compile_Test\00_SW\00_SW_DEV\misc\compile_test\test_report\pwm_flicker_Compile_Test.xml' is an invalid file.
16:19:37 WARNING: At line 3 of file:/D:/Jenkins/workspace/Balboa_Compile_Test/00_SW/00_SW_DEV/misc/compile_test/test_report/pwm_flicker_Compile_Test.xml:cvc-pattern-valid: 对于类型为 '#AnonType_timetestsuite' 的模式 '(([0-9]{0,3},)*[0-9]{3}|[0-9]{0,3})*(\.[0-9]{0,3})?', 值 '13.51552677154541' 不具有面有效性。
16:19:37 WARNING: At line 3 of file:/D:/Jenkins/workspace/Balboa_Compile_Test/00_SW/00_SW_DEV/misc/compile_test/test_report/pwm_flicker_Compile_Test.xml:cvc-attribute.3: 在元素 'testsuite' 中, 属性 'time' 的值 '13.51552677154541' 与其类型 'null' 不匹配。
16:19:37 FATAL: The result file 'D:\Jenkins\workspace\Balboa_Compile_Test\00_SW\00_SW_DEV\misc\compile_test\test_report\pwm_flicker_Compile_Test.xml' for the metric 'JUnit' is not valid. The result file has been skipped.
```

解决：

根据日志进一步分析，发现生成的报告中，&lt;testsuite name="XXX" time="13.51552677154541" tests="67" failures="0" errors="0" skipped="0" &gt;时间为小数点13位，可能Jenkins无法解析，改为小数点后6位，也不能解析，4位也不能解析，最终发现2位可以解析，不确定是否该版本的Jenkins做了什么严格匹配，修改脚本，完工。

```
time = '13.51552677154541'
write_line = '<testsuite name="XXX" time="{:.2f}" tests="67" failures="0" errors="0" skipped="0" >'.format(time)
print(write_line)
<testsuite name="XXX" time="13.51" tests="67" failures="0" errors="0" skipped="0" >
```



