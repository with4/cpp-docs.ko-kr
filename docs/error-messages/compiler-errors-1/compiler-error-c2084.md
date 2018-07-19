---
title: 컴파일러 오류 C2084 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce1510dd6e78b8774d3cc433f583c16cdbb8d06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33173879"
---
# <a name="compiler-error-c2084"></a>컴파일러 오류 C2084
함수 '*함수*' 이미 본문이  
  
 함수가 이미 정의 되었습니다.  
  
 버전의 Visual Studio 2002 년 이전 Visual c + +  
  
-   하지만 추가 정의 사용할 수 없는 컴파일러는 동일한 실제 형식으로 확인 하는 여러 템플릿 특수화를 수락 합니다. 이제 컴파일러는 이러한 여러 정의 검색 합니다.  
  
-   `__int32` 및 `int` 별도 형식으로 간주 되었습니다. 컴파일러가 이제 처리 `__int32` 동의어로 `int`합니다. 즉, 컴파일러는 함수는 모두에 대해 오버 로드 하는 경우 정의가 여러 개 검색 하는지 `__int32` 및 `int` 오류가 발생 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2084 오류가 생성 됩니다.  
  
```cpp  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
이 오류를 해결 하려면 중복 정의 제거 합니다.  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```