---
title: "typeof 대신 T::typeid 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof 키워드"
  - "typeid 키워드[C++]"
  - "typeid 연산자"
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# typeof 대신 T::typeid 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Managed Extensions for C\+\+에 사용되는 `typeof` 연산자는 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 `typeid` 키워드로 대체되었습니다.  
  
 Managed Extensions에서 `__typeof()` 연산자는 관리되는 형식의 이름을 전달할 때 관련 `Type*` 개체를 반환합니다.  예를 들면 다음과 같습니다.  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 새 구문에서 `__typeof`는 관리되는 형식을 지정한 경우 `Type^`을 반환하는 `typeid`라는 추가 형식로 대체되었습니다.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## 참고 항목  
 [일반적인 언어 변경 사항](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)