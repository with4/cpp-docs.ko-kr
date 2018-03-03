---
title: "컴파일러 오류 C3421 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3421
dev_langs:
- C++
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b702bd6481041599c8ed67cf5f7e2443864bf0a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3421"></a>컴파일러 오류 C3421
'type': 이 클래스의 종료자는 액세스할 수 없거나 존재하지 않으므로 호출할 수 없습니다.  
  
 종료자는 암시적으로 비공개이므로 바깥쪽 형식 외부에서 호출될 수 없습니다.  
  
 자세한 내용은 참조 [소멸자 및 종료자에서 하는 방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3421을 생성합니다.  
  
```  
// C3421.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B {   
   !B() {}  
  
public:  
   ~B() {}  
};  
  
int main() {  
   A a;  
   a.!A();   // C3421  
  
   B b;  
   b.!B();   // C3421  
}  
```