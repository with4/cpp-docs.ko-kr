---
title: "cpp_quote | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.cpp_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cpp_quote attribute"
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# cpp_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 문자열을 따옴표 없이 생성 된.idl 파일에 내보냅니다.  
  
## 구문  
  
```  
  
      [ cpp_quote(  
   "statement"  
) ];  
```  
  
#### 매개 변수  
 *statement*  
 C 명령입니다.  
  
## 설명  
 **Cpp\_quote** C\+\+ 특성입니다.idl 파일에 전처리기 지시문을 배치 하려는 경우에 유용 합니다.  
  
 수도 있습니다  **cpp\_quote** 및.h 파일을 MIDL 컴파일의 일부로 생성 합니다.  C \+ \+ IDL 특성을 사용 하지만 몇 가지 작업에 대해 사용할 수 없습니다이 파일은 C\+\+ 헤더 파일에 있는 경우 예를 들어, 다음을 사용할 수 있어야 하는 MIDL에서 생성 하는.h 파일 만들기를 컴파일할 수 있습니다.  
  
 **Cpp\_quote** 특성을 동일한 기능을가지고 있는  [cpp\_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL 속성.  
  
## 예제  
 예제를 보려면  [듀얼](../windows/dual.md) 사용 하는 방법에 대 한 예제 사용 하 여  **cpp\_quote**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)