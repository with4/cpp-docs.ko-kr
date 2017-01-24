---
title: "컴파일러 오류 C2017 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2017"
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이스케이프 시퀀스가 잘못되었습니다.  
  
 이스케이프 시퀀스\(예: \\t\)가 문자열 상수나 문자 외부에 표시됩니다.  
  
 다음 샘플에서는 C2017 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 C2017 오류는 이스케이프 시퀀스가 포함된 문자열과 함께 문자열화 연산자를 사용하는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2017 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```