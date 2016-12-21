---
title: "wbuffer_convert 클래스 | Microsoft Docs"
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
  - "stdext::cvt::wbuffer_convert"
  - "wbuffer_convert"
  - "stdext.cvt.wbuffer_convert"
  - "cvt.wbuffer_convert"
  - "cvt::wbuffer_convert"
  - "wbuffer/stdext::cvt::wbuffer_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wbuffer_convert 클래스"
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wbuffer_convert 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

바이트 스트림 버퍼에서 나가고 들어오는 요소의 전송을 제어하는 스트림 버퍼에 대해 설명합니다.  
  
## 구문  
  
```  
template<class Codecvt,  
    class Elem = wchar_t,  
    class Traits = std::char_traits<Elem>  
>  
    class wbuffer_convert  
        : public std::basic_streambuf<Elem, Traits>  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Codecvt`|변환 개체를 나타내는 [로캘](../standard-library/locale-class.md) 패싯입니다.|  
|`Elem`|와이드 문자 요소 형식입니다.|  
|`Traits`|*Elem*과 연결된 특성입니다.|  
  
## 설명  
 이 템플릿 클래스는 `std::streambuf` 형식의 바이트 스트림 버퍼에서 나가고 들어오는 `_Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명하며, 해당 문자 특성은 `Traits` 클래스로 설명합니다.  
  
 `Elem` 값 시퀀스와 멀티바이트 시퀀스 간 변환은 클래스 `Codecvt<Elem, char, std::mbstate_t>`의 개체에 의해 수행되며, 표준 코드 변환 패싯 `std::codecvt<Elem, char, std::mbstate_t>`의 요구 사항을 충족합니다.  
  
 이 템플릿 클래스의 개체는 다음을 저장합니다.  
  
-   기본 바이트 스트림 버퍼에 대한 포인터  
  
-   할당된 변환 개체에 대한 포인터\([wbuffer\_convert](../standard-library/wbuffer-convert-class.md) 개체가 제거될 때 해제됨\)  
  
-   [state\_type](../Topic/wbuffer_convert::state_type.md) 형식의 변환 상태 개체  
  
### 생성자  
  
|||  
|-|-|  
|[wbuffer\_convert](../Topic/wbuffer_convert::wbuffer_convert.md)|`wbuffer_convert` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[state\_type](../Topic/wbuffer_convert::state_type.md)|변환 상태를 나타내는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[rdbuf](../Topic/wbuffer_convert::rdbuf.md)|바이트 스트림 버퍼를 반환합니다.|  
|[상태](../Topic/wbuffer_convert::state.md)|변환의 상태를 나타내는 개체를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std