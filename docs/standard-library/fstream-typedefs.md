---
title: "&lt;fstream&gt; typedefs | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 55a148c472048c5531521cd6f4574477e7c31cac
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; 형식 정의
||||  
|-|-|-|  
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|  
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|  
|[wifstream](#wifstream)|[wofstream](#wofstream)|  
  
##  <a name="filebuf"></a>  filebuf  
 `char` 템플릿 매개 변수에서 특수화된 `basic_filebuf` 형식입니다.  
  
```
typedef basic_filebuf<char, char_traits<char>> filebuf;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_filebuf](../standard-library/basic-filebuf-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="fstream"></a>  fstream  
 `char` 템플릿 매개 변수에서 특수화된 `basic_fstream` 형식입니다.  
  
```
typedef basic_fstream<char, char_traits<char>> fstream;
```  
  
### <a name="remarks"></a>설명  
 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_fstream](../standard-library/basic-fstream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="ifstream"></a>  ifstream  
 파일에서 직렬로 싱글바이트 문자 데이터를 읽는 데 사용할 스트림을 정의합니다. `ifstream`은 `basic_ifstream`에 대한 `char` 템플릿 클래스를 특수화하는 typedef입니다.  
  
 `wifstream` 더블 와이드 문자를 읽도록 `basic_ifstream`을 특수화하는 typedef인 `wchar_t`도 있습니다. 자세한 내용은 [wifstream](../standard-library/fstream-typedefs.md#wifstream)을 참조하세요.  
  
```
typedef basic_ifstream<char, char_traits<char>> ifstream;
```  
  
### <a name="remarks"></a>설명  
 형식은 기본 문자 특성을 포함하는 char 형식의 요소용으로 특수화된 `basic_ifstream` 템플릿 클래스의 동의어입니다. 예제는 다음과 같습니다.  
  
 `using namespace std;`  
  
 `ifstream infile("existingtextfile.txt");`  
  
 `if (!infile.bad())`  
  
 `{`  
  
 `// Dump the contents of the file to cout.`  
  
 `cout << infile.rdbuf();`  
  
 `infile.close();`  
  
 `}`  
  
##  <a name="ofstream"></a>  ofstream  
 `char` 템플릿 매개 변수에서 특수화된 `basic_ofstream` 형식입니다.  
  
```
typedef basic_ofstream<char, char_traits<char>> ofstream;
```  
  
### <a name="remarks"></a>설명  
 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_ofstream](../standard-library/basic-ofstream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="wfstream"></a>  wfstream  
 `wchar_t` 템플릿 매개 변수에서 특수화된 `basic_fstream` 형식입니다.  
  
```
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```  
  
### <a name="remarks"></a>설명  
 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_fstream](../standard-library/basic-fstream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="wifstream"></a>  wifstream  
 `wchar_t` 템플릿 매개 변수에서 특수화된 `basic_ifstream` 형식입니다.  
  
```
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```  
  
### <a name="remarks"></a>설명  
 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_ifstream](../standard-library/basic-ifstream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="wofstream"></a>  wofstream  
 `wchar_t` 템플릿 매개 변수에서 특수화된 `basic_ofstream` 형식입니다.  
  
```
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```  
  
### <a name="remarks"></a>설명  
 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_ofstream](../standard-library/basic-ofstream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="wfilebuf"></a>  wfilebuf  
 `wchar_t` 템플릿 매개 변수에서 특수화된 `basic_filebuf` 형식입니다.  
  
```
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_filebuf](../standard-library/basic-filebuf-class.md) 템플릿 클래스의 동의어입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<fstream>](../standard-library/fstream.md)




