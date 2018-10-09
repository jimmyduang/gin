[TOC]
# package utils

 import "admin/utils"

 > `utils`包实现了加解密，字符串，时间，Token，输入校验，自定义错误等公共方法的实现。

## index

###  des.go
###  es.go
###  hex_info.go
#### 对用户电话号码进行混淆

```
    HexPhone(phone string) string
```

`HexPhone`是对用户电话号码进行混淆
#### 对用户邮箱进行混淆
```
    HexEmail(email string) string
```

`HexEmail`是对用户邮箱进行混淆
#### 对用户QQ号码进行混淆
```
    HexQQ(QQ string) string
```

`HexQQ`是对用户QQ号码进行混淆

###  main.go
###  rdtsc_decl.go
###  string.go
#### 取指定长度的字符串
```
   Substr(str string, start, length int) string
```

`Substr`取指定长度的字符串
#### 指定位置插入字符串
```
   func InsertStr(str, inser string, start int) string
```

`InsertStr`指定位置插入字符串
#### 各种类型转字符串
```
   func InterfaceToString(inter interface{}) string
```

`InterfaceToString`interface类型转成字符串
#### byte转字符串
```
   func ByteToString(b []byte) string
```

`ByteToString`byte转字符串
#### func 混淆银行卡号
```
   func BankStr(str string) string
```

`BankStr`混淆银行卡号
#### 返回手机/邮箱等， 这种格式 135****1234
```
  func PrivacyInfoBasic(str string) string
```

`PrivacyInfoBasic` 返回手机/邮箱等， 这种格式 135****1234
#### 隐私信息保护，手机/邮箱/QQ
```
   func PrivacyInfo(str string) string
```

`PrivacyInfo`隐私信息保护，手机/邮箱/QQ
#### 去除字符串右边的符号
```
   func Rtirm(str, tt string) string
```

`Rtirm`去除字符串右边的符号
###  strings.go
###  times.go
###  timetools.go
#### 格式化时间参数`2006-01-02 15:04:05`
```
    var C_format_datetime string = "2006-01-02 15:04:05"
```
#### 格式化时间参数`2006-01`
```
    var C_format_datemonth string = "2006-01"
```
#### 格式化时间参数`2006-01-02`
```
    var C_format_date_ymd string = "2006-01-02"
```
#### 判断两个字符串日期相差的天数
```
   func DifferDays(startDate, endDate string) int
```

`DifferDays`判断两个字符串日期相差的天数
#### 获取指定月份天数
```
   func GetMonthDays(str string) int
```

`GetMonthDays`获取指定月份天数
#### 获取当月天数
```
   func GetThisMonthDays() int
```

`GetThisMonthDays`获取当月天数
#### 统一日期格式
```
   func FormatDateString(str, strFormat, dateFormat string, start, length int) string
```

`FormatDateString`统一日期格式
#### 计算时差返回字符串
```
/**
* 计算时差返回字符串
* 字符串类型:   2006-01-02 15:04:05
 */
   func TimeDiffString(dateStr, timeDiff string) string
```

`TimeDiffString`计算时差返回字符串,字符串类型:   `2006-01-02 15:04:05`
#### 格式化字符串为时间戳
```
   func FormatStr2Unix(date string, format string) (int64, error)
```

`FormatStr2Unix`格式化字符串为时间戳
#### 时间戳转日期
```
/*
 * 格式化字符串为时间戳
 * @date 待转化为时间戳的字符串
 * @format 转化所需模板 如 20060102
 */
   func FormatUnix2Str(time_unix int64, format string) string
```

`FormatUnix2Str`时间戳转日期
#### 格式化字符串北京时间
```
/*
 * 时间戳转日期
 * @time_unix 时间戳
 * @format 转化所需模板 如 20060102
 */
   func FormatDateCCT(format, date string) (time.Time, error)
```

`FormatDateCCT`格式化字符串北京时间
#### 获取当前时间和当前时间相差的一段时间
```
/*
 * 获取
 * 2016-11-xx 00:00:00
 * 2016-11-xx 23:59:59
 */
   func GetSDateAndEDateSJC(sjc int) (string, string) 
```

`GetSDateAndEDateSJC`获取当前时间和当前时间相差的一段时间`2016-11-xx 00:00:00` `2016-11-xx 23:59:59`
#### 获取上周一到周天
```
   func GetSDateAndEDateSJCmond2sun(sjc int) (string, string)
```

`GetSDateAndEDateSJCmond2sun`获取上周一到周天`2016-11-xx 00:00:00` `2016-11-xx 23:59:59`
#### 获取现在日期时间
```
   func GetNowDatetime(format string) string
```

`GetNowDatetime`获取现在日期时间
#### 改变日期
```
/*
* 改变日期
* @time_date 要改变的日期
* @format 转化所需模板 如 20060102
* @years 增加或减少的年
* @months 增加或减少的月
* @days 增加或减少的日
 */
 func ChangeDate(time_date, format string, years int, months int, days int) string
```

`ChangeDate`改变日期
#### 获取两个时间间隔内的所有日期
```
/**
* 获取两个时间间隔内的所有日期
* 单位是天
 */
func GetDateDiff(time_date, format string, days int) []string
```

`GetDateDiff`获取两个时间间隔内的所有日期
#### 获取本周周一的日期
```
/*
获取本周一的日期
return 2017-04-17
*/
 func GetMonday() string
```

`GetMonday`获取本周周一的日期
#### 增加或者减少当前时间
```
/*
增加或者减少当前时间
@cha_str	= -3h;当前时间减少3小时
@format	返回时间的格式
*/
  func ChangeDateByNow(cha_str, format string) string
```

`ChangeDateByNow`增加或者减少当前时间
#### 获取今天开始和结束时间的时间戳
```
   func GetTodayUnix() (int64, int64)
```

`GetTodayUnix`获取今天开始和结束时间的时间戳
#### 获取今天开始和结束时间的时间戳字符串
```
   func GetTodayUnixStr() (string, string)
```

`GetTodayUnixStr`获取今天开始和结束时间的时间戳字符串
#### 获取今天的开始和结束时间
```
   func GetTodayDate() (string, string) 
```

`GetTodayDate`获取今天的开始和结束时间
#### 获取上周六周日的开始结束时间
```
   func GetSaturdaySundy() (string, int, int)
```

`GetSaturdaySundy`获取上周六周日的开始结束时间
#### 获取周1 至 周5的开始结束时间
```
   func GetAllWeek() []int
```

`GetAllWeek`去除字符串右边的符号
###  token.go
###  validate.go
###  yaboError.go
#### 结构体
```
   //自定义的出错结构
type YaboError struct {
	ErrMsg string
}
```
#### 实现Error接口
```
func (e YaboError) Error() string
```

`Error`实现Error接口






