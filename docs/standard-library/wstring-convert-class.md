---
title: "wstring_convert 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvt.wstring_convert"
  - "wstring_convert"
  - "stdext::cvt::wstring_convert"
  - "cvt::wstring_convert"
  - "wstring/stdext::cvt::wstring_convert"
  - "stdext.cvt.wstring_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wstring_convert 클래스"
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
caps.latest.revision: 25
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wstring_convert 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스 `wstring_convert`는 와이드 문자열과 바이트 문자열 간의 변환을 수행합니다.  
  
## 구문  
  
```  
template<  
    class Codecvt,  
    class Elem = wchar_t  
>  
class wstring_convert  
```  
  
#### 매개 변수  
 Codecvt  
 변환 개체를 나타내는 [로캘](../standard-library/locale-class.md) 패싯입니다.  
  
 Elem  
 와이드 문자 요소 형식입니다.  
  
## 설명  
 템플릿 클래스는 `std::basic_string<Elem>` 클래스의 와이드 문자열 개체와 `std::basic_string<char>` 클래스\(`std::string`이라고도 함\)의 바이트 문자열 개체 간 변환을 제어하는 개체를 설명합니다. 템플릿 클래스는 `wide_string` 및 `byte_string` 형식을 이러한 두 형식의 동의어로 정의합니다.`Elem` 값\(`wide_string` 개체에 저장\) 시퀀스와 멀티바이트 시퀀스\(`byte_string` 개체에 저장\) 간의 변환은 표준 코드 변환 패싯 `std::codecvt<Elem, char, std::mbstate_t>`의 요구 사항을 충족하는 `Codecvt<Elem, char, std::mbstate_t>` 클래스의 개체에 의해 수행됩니다.  
  
 이 템플릿 클래스의 개체는 다음을 저장합니다.  
  
-   오류 발생 시 표시할 바이트 문자열  
  
-   오류 발생 시 표시할 와이드 문자열  
  
-   할당된 변환 개체에 대한 포인터\(wbuffer\_convert 개체가 제거될 때 해제됨\)  
  
-   [state\_type](../Topic/wstring_convert::state_type.md) 형식의 변환 상태 개체  
  
-   변환 개수  
  
### 생성자  
  
|||  
|-|-|  
|[wstring\_convert](../Topic/wstring_convert::wstring_convert.md)|`wstring_convert` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[byte\_string](../Topic/wstring_convert::byte_string.md)|바이트 문자열을 나타내는 형식입니다.|  
|[wide\_string](../Topic/wstring_convert::wide_string.md)|와이드 문자열을 나타내는 형식입니다.|  
|[state\_type](../Topic/wstring_convert::state_type.md)|변환 상태를 나타내는 형식입니다.|  
|[int\_type](../Topic/wstring_convert::int_type.md)|정수를 나타내는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[from\_bytes](../Topic/wstring_convert::from_bytes.md)|바이트 문자열을 와이드 문자열로 변환합니다.|  
|[to\_bytes](../Topic/wstring_convert::to_bytes.md)|와이드 문자열을 바이트 문자열로 변환합니다.|  
|[converted](../Topic/wstring_convert::converted.md)|성공적인 변환 수를 반환합니다.|  
|[상태](../Topic/wstring_convert::state.md)|변환의 상태를 나타내는 개체를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std