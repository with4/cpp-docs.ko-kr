---
title: "컴파일러 경고 (수준 1) C4067 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4067
dev_langs: C++
helpviewer_keywords: C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 90c29e7bc63096a6e46d4febda9c66d2759bb06a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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