---
title: 컴파일러 경고 (수준 1) C4350 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7e13b73eeee9c24841e97419b702b3e41be3982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4350"></a>컴파일러 경고(수준 1) C4350
동작 변경: 'member1'이(가) 'member2' 대신 호출됩니다.  
  
 비 const 참조에는 rvalue는 바인딩할 수 없습니다. Visual Studio 2003 이전 Visual c + + 버전에서는 직접 초기화의 비 const 참조는 rvalue를 바인딩할 수 있었습니다. 이제이 코드는 경고를 제공합니다.  
  
 이전 버전과 호환성에 대 한 비 const 참조에 대 한 rvalue에 바인딩할 수도 있지만 가능한 경우 표준 변환은 기본 설정 됩니다.  
  
 이 경고는 Visual c + +.NET 2002 컴파일러에서 변경이 된 동작을 나타냅니다. 설정 된 경우이 경고 수 제시 됩니다 올바른 코드입니다. 예를 들어 것 주어질 수 사용 하는 경우는 **auto_ptr** 클래스 템플릿을 합니다.  
  
 이 경고를 발생 하는 경우 비 const 참조에 대 한 rvalue에 종속 된 경우를 확인 하기 위해 코드를 검사 합니다. 상수 참조를 추가 하거나 추가 const 참조 오버 로드를 제공 하는 문제를 해결할 수 있습니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.  
  
 다음 샘플에서는 C4350 오류가 생성 됩니다.  
  
```cpp  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead:  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```