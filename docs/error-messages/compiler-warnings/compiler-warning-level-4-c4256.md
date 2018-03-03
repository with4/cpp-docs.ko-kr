---
title: "컴파일러 경고 (수준 4) C4256 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4256
dev_langs:
- C++
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4bbaec27948f061cb21eeb432446517d4f9a6b2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4256"></a>컴파일러 경고(수준 4) C4256
'function': 가상 기본 클래스 생성자가 '...'; 호출이 이전 버전의 Visual c + +와 호환 되지 않을 수 있습니다.  
  
 호환 되지 않을 수도 있습니다.  
  
 다음 코드 예제를 살펴봅니다. 경우 S2::S2 생성자 정의 (int i,...) 버전 7 이전의 Visual c + + 컴파일러의 버전을 사용 하 여 컴파일된 하지만 다음 예에서는 현재 버전을 사용 하 여 컴파일된, 인해 s 3에 대 한 생성자에 대 한 호출 연결이 올바르게 작동 하지 않습니다 특별 한 경우 호출 규칙 변경 합니다. 두 항목이 모두 Visual C++ 6.0을 사용해서 컴파일된 경우, 줄임표에 대해 전달된 매개 변수가 없지 않은 한 어느 항목에서도 호출이 올바르게 작동하지 않습니다.  
  
 이 경고를 해결 하려면  
  
1.  생성자에서 줄임표 (...)를 사용 하지 마십시오.  
  
2.  프로젝트에 포함 된 모든 구성 요소 (모든 라이브러리를 정의 하거나이 클래스를 참조 하는 포함), 현재 버전으로 작성 된 다음 사용 하 여 경고를 사용 하지 않도록 설정 되었는지 확인는 [경고](../../preprocessor/warning.md) pragma입니다.  
  
 다음 샘플에서는 C4256 오류가 생성 됩니다.  
  
```  
// C4256.cpp  
// compile with: /W4  
// #pragma warning(disable : 4256)  
struct S1  
{  
};  
  
struct S2: virtual public S1  
{  
   S2( int i, ... )    // C4256  
   {  
      i = 0;  
   }  
   /*  
   // try the following line instead  
   S2( int i)  
   {  
      i = 0;  
   }  
   */  
};  
  
void func1()  
{  
   S2 S3( 2, 1, 2 );   // C4256  
   // try the following line instead  
   // S2 S3( 2 );  
}  
  
int main()  
{  
}  
```