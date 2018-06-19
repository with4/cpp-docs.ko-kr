---
title: 컴파일러 오류 C3465 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3465
dev_langs:
- C++
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1965b616ec3eb8c7de50f3a76b10e41f3579954c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254038"
---
# <a name="compiler-error-c3465"></a>컴파일러 오류 C3465
'type' 형식을 사용하려면 'assembly' 어셈블리를 참조해야 합니다.  
  
 클라이언트를 다시 컴파일할 때까지 형식 전달은 클라이언트 응용 프로그램에 대해 작동합니다. 다시 컴파일하는 경우에는 클라이언트 응용 프로그램에서 사용하는 형식의 정의를 비롯하여 모든 어셈블리에 대한 참조가 필요합니다.  
  
 자세한 내용은 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 형식의 새 위치를 포함하는 어셈블리를 빌드합니다.  
  
```  
// C3465.cpp  
// compile with: /clr /LD  
public ref class R {  
public:  
   ref class N {};  
};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 형식의 정의를 포함하는 데 사용한 어셈블리를 빌드하지만 이제는 형식에 대한 전달 구문을 포함합니다.  
  
```  
// C3465_b.cpp  
// compile with: /clr /LD  
#using "C3465.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3465를 생성합니다.  
  
```  
// C3465_c.cpp  
// compile with: /clr  
// C3465 expected  
#using "C3465_b.dll"  
// Uncomment the following line to resolve.  
// #using "C3465.dll"  
  
int main() {  
   R^ r = gcnew R();  
}  
```