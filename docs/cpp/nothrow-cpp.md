---
title: nothrow (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: nothrow_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 82370900fc96c97665cb35351605db86c9ff4faf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="nothrow-c"></a>nothrow (C++)
**Microsoft 전용**  
  
 함수 선언에서 사용할 수 있는 `__declspec` 확장 특성입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## <a name="remarks"></a>설명  
 이 특성은 컴파일러에게 선언한 함수와 이 함수가 요청한 함수들이 예외를 throw하지 않도록 명령합니다. 이제 기본값인, 동기 예외 처리 모델을 이용하여 컴파일러는 해제할 수 있는 특정 개체의 수명 추적 메커니즘을 제거할 수 있으며, 코드 크기를 크게 줄일 수 있습니다. 다음 전처리기 지시문을 제공할 경우 아래 세 가지 함수 선언은 동일합니다.  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 `void __declspec(nothrow) __stdcall f2();`을 사용하면, 함수 집합에서 `#define`를 쉽게 지정하기 위해 `nothrow`문을 가지고 설명한 것처럼 API 정의를 사용할 수 있다는 장점이 있습니다. 세 번째 선언`, void __stdcall f3() throw();`은 C++ 표준에 따라 정의된 구문입니다.  
  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)