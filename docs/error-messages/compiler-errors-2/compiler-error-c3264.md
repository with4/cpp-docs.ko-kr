---
title: "컴파일러 오류 C3264 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3264
dev_langs:
- C++
helpviewer_keywords:
- C3264
ms.assetid: 94ece687-2364-4f7a-8ebb-7afd3ae9d63d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c5dc129754774f5dc8193d7a43bb982a8768c582
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3264"></a>컴파일러 오류 C3264
'class': 클래스-생성자는 반환 형식을 가질 수 없습니다.  
  
클래스 생성자가 반환 형식을 가질 수 없습니다.  
  
다음 샘플에서는 C3264를 생성합니다.  
  
```  
// C3264_2.cpp  
// compile with: /clr  
  
ref class X {  
   public:  
      static int X()   { // C3264  
      }  
  
      /* use the code below to resolve the error  
      static X() {  
      }  
      */  
};  
int main() {  
}  
```  

