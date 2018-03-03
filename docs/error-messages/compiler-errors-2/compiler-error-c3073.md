---
title: "컴파일러 오류 C3073 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3073
dev_langs:
- C++
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 046b1d17ea0264e01a4acd9eb93e5babb826b756
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3073"></a>컴파일러 오류 C3073
'type': ref 클래스에는 사용자 정의 복사 생성자가 없습니다  
  
 에 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일, 컴파일러는 참조 형식에 대 한 복사 생성자를 생성 하지 것입니다. 모든 **/clr** 컴파일, 인스턴스를 복사 하는 유형의 경우 참조 형식에 대 한 복사 생성자를 직접 정의 해야 합니다.  
  
 자세한 내용은 참조 [참조 형식에 대 한 c + + 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3073 오류가 발생 합니다.  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```