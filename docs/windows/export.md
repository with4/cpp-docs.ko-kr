---
title: "export | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "export attribute"
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# export
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.Idl 파일에 추가할 수 있는 데이터 구조를 인해 발생 합니다.  
  
## 구문  
  
```  
  
[export]  
  
```  
  
## 설명  
 해당  **내보내기** C\+\+ 특성 인해.idl 파일에 배치할 수 및 다음 형식 라이브러리는 모든 언어를 사용할 수 있도록 이진 호환 형식에서에 사용할 수 있도록 하는 데이터 구조입니다.  
  
 적용할 수 없습니다.는  **내보내기** 특성 클래스에 public 멤버 클래스를만 있는 경우에 \(해당 하는 있는 `struct`\).  
  
 명명 되지 않은 내보낼 경우 `enum`s 또는 `struct`s가 수 이름이 시작  **\_\_unnamed***x*, 어디  *x* 은 일련 번호입니다.  
  
 내보내기에 대 한 올바른 형식 정의 된 기본 형식, 구조체, 공용 구조체, 열거형 또는 형식 식별자입니다.  참조 하십시오  [형식 정의](http://msdn.microsoft.com/library/windows/desktop/aa367287) 에 대 한 자세한 내용은.  
  
## 예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 있는  **내보내기** 특성:  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**union**, `typedef`, `enum`, `struct`, or`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)