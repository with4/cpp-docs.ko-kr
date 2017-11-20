---
title: "컴파일러 오류 C2951 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2951
dev_langs: C++
helpviewer_keywords: C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4be1b3a298fc24572fcc44b9deb031c0d49b7332
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2951"></a>컴파일러 오류 C2951
형식 선언은 전역, 네임 스페이스 에서만 허용 됩니다 또는 클래스 범위  
  
 제네릭 또는 템플릿 클래스 외부 전역 또는 네임 스페이스 범위를 선언할 수 없습니다. 포함 파일에 두 제네릭 또는 템플릿 선언 하는 경우에 전역 범위에서 포함 파일 인지 확인 합니다.  
  
 다음 샘플에서는 C2951 오류가 생성 됩니다.  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 C2951은 제네릭을 사용 하는 경우에 발생할 수 있습니다.  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```