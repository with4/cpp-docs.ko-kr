---
title: "컴파일러 경고 (수준 3) C4398 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 18270bb89bcc5d1855750c572a5b6fb9e51c2ba3
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4398"></a>컴파일러 경고(수준 3) C4398
'variable': 프로세스별 전역 개체가 올바르게 작동 하지 않을 수도 여러 appdomain; __declspec (appdomain)을 사용 하는 것이 좋습니다.  
  
 사용 하는 가상 함수 [__clrcall](../../cpp/clrcall.md) 네이티브 형식에 규칙을 호출 하면 생성 된 응용 프로그램 별로 도메인 vtable. 이러한 변수에 올바르지 않을 수 있습니다 여러 응용 프로그램 도메인에서 사용 하는 경우.  
  
 명시적으로 변수를 표시 하 여이 경고를 해결할 수 `__declspec(appdomain)`합니다. Visual Studio 2017 이전에 Visual Studio의 버전을 사용 하 여 컴파일할이 경고를 해결할 수 **/clr: pure**, 기본적으로 appdomain 별 전역 변수를 만드는 합니다.  
  
 자세한 내용은 참조 [appdomain](../../cpp/appdomain.md) 및 [응용 프로그램 도메인 및 Visual c + +](../../dotnet/application-domains-and-visual-cpp.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4398 오류가 발생 합니다.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```
