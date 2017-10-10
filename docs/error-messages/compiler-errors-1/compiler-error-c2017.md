---
title: "컴파일러 오류 C2017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2017
dev_langs:
- C++
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7170fa404cba6cab3a0fcf3eec3e1d02c11271bb
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2017"></a>컴파일러 오류 C2017
잘못 된 이스케이프 시퀀스  
  
 예: \t 이스케이프 시퀀스를 문자 또는 문자열을 외부에 나타나며 상수입니다.  
  
 다음 샘플에서는 C2017 오류가 생성 됩니다.  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 C2017은 문자열 화 연산자가 이스케이프 시퀀스가 포함 된 문자열을 함께 사용 하는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2017 오류가 생성 됩니다.  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```
