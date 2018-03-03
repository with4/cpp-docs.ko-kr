---
title: "컴파일러 오류 C3063 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3063
dev_langs:
- C++
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 764cebae9e95992ba3d5ffa1773af4802c489392
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3063"></a>컴파일러 오류 C3063
연산자 'operator': 모든 피연산자 열거형 형식이 있어야 합니다.  
  
열거자에 대해 연산자를 사용할 때는 두 피연산자 모두 열거형 형식 이어야 합니다. 자세한 내용은 참조 [하는 방법: C + 열거형 정의 및 사용 + CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)합니다.  
  
## <a name="example"></a>예  
다음 샘플에서는 C3063 경고가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```