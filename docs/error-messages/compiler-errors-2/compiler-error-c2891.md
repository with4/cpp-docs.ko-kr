---
title: 컴파일러 오류 C2891 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01741d1cc67f0045c46ab392212625b9e1a2d8ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246372"
---
# <a name="compiler-error-c2891"></a>컴파일러 오류 C2891
'parameter': 템플릿 매개 변수의 주소를 가져올 수 없습니다  
  
 Lvalue 경우가 아니라면 템플릿 매개 변수 주소를 가져올 수 없습니다. 형식 매개 변수가 주소가 없기 때문에 lvalue 않습니다. Lvalue 없는 템플릿 매개 변수 목록에 비형식 값도 주소를가지고 하지 않습니다. 이 템플릿 매개 변수로 전달 된 값에는 템플릿 인수는 컴파일러 생성 복사 이므로 컴파일러 오류 C2891 하는 코드의 예시입니다.  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 템플릿 매개 변수를 lvalue 참조 형식에 같은 수의 주소는 수행 했습니다.  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 이 오류를 해결 하려면 lvalue 하지 않은 주소는 템플릿 매개 변수를 사용 하지 않습니다.