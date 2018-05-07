---
title: 컴파일러 경고 (수준 1) C4067 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4067
dev_langs:
- C++
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eccec985e6a9e652f18c6513542942351ff6efc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4067"></a>컴파일러 경고 (수준 1) C4067
예기치 않은 토큰이 전처리기 지시문 다음에 줄 바꿈이 필요 합니다.  
  
 컴파일러 발견 하 여 전처리기 지시문 다음에서 추가 문자를 무시 합니다. 이 경고는 ANSI 호환성 인 경우에 표시 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
```  
// C4067a.cpp  
// compile with: /DX /Za /W1  
#pragma warning(default:4067)  
#if defined(X)  
#else  
#endif v   // C4067  
int main()  
{  
}  
```  
  
### <a name="to-resolve-this-warning-try-the-following"></a>이 경고를 해결 하려면 다음을 시도 합니다.  
  
1.  사용 하 여 컴파일 **/Ze**합니다.  
  
2.  주석 구분 기호를 사용 합니다.  
  
```  
// C4067b.cpp  
// compile with: /DX /Za /W1  
#if defined(X)  
#else  
#endif  
int main()  
{  
}  
```