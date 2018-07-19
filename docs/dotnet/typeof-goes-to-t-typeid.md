---
title: Typeof T::typeid | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0ae9f772a68735555748e6edbeb6196f1a73d2c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164520"
---
# <a name="typeof-goes-to-ttypeid"></a>typeof 대신 T::typeid 사용
`typeof` c + +로 변경 된가 데에 대 한 관리 되는 확장에 사용 되는 연산자는 `typeid` Visual c + +의 키워드입니다.  
  
 Managed extensions에서는 `__typeof()` 연산자는 관련 된 반환 `Type*` 개체의 관리 되는 형식 이름을 전달 하는 경우. 예를 들어:  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 새 구문에서 `__typeof` 라는 추가 형식으로 대체 되었습니다 `typeid` 반환 하는 `Type^` 관리 되는 형식 지정 된 경우.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## <a name="see-also"></a>참고 항목  
 [일반적인 언어 변경 사항 (C + + /cli CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)