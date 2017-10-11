---
title: "컴파일러 오류 C2087 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2087
dev_langs:
- C++
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 047c58d495233ba69d8d688696b80aa756bb9462
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2087"></a>컴파일러 오류 C2087
'identifier': 첨자 누락  
  
 여러 첨자가 포함 된 배열 정의 하나 이상의 차원에 대 한 첨자 값이 없습니다.  
  
 다음 샘플에서는 C2087 오류가 생성 됩니다.  
  
```  
// C2087.cpp  
int main() {  
   char a[10][];   // C2087  
}  
```  
  
 해결 방법:  
  
```  
// C2087b.cpp  
int main() {  
   char b[4][5];  
}  
```
