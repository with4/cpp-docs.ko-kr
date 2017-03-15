---
title: "컴파일러 오류 C3069 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3069
dev_langs:
- C++
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 6cb151dcb6f96ec897eea5cea126ed23f68d147c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3069"></a>컴파일러 오류 C3069
'operator': 열거형 형식에 사용할 수 없습니다.  
  
 CLR 열거형에 대해서는 연산자가 지원되지 않습니다.  자세한 내용은 참조 [하는 방법: C + 열거형 정의 및 사용 + CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3069를 생성합니다.  
  
```  
// C3069.cpp  
// compile with: /clr  
enum struct E { e1 };  
enum F { f1 };  
  
int main() {  
   E e = E::e1;  
   bool tf;  
   tf = !e;   // C3069  
  
   // supported for native enums  
   F f = f1;  
   tf = !f;  
}  
```
