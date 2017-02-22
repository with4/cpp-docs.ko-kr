---
title: "컴파일러 경고 (수준 4) C4820 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4820"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4820"
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 4) C4820
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bytes'바이트 채움 문자가 construct 'member\_name' 뒤에 추가되었습니다.  
  
 요소의 형식과 순서로 인해 컴파일러에서 구조체의 끝에 채움 문자를 추가했습니다.  구조체의 채움 문자에 대한 자세한 내용은 [align](../../cpp/align-cpp.md)을 참조하십시오.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4820 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4820.cpp  
// compile with: /W4 /c  
#pragma warning(default : 4820)   
  
// Delete the following 4 lines to resolve.  
__declspec(align(2)) struct MyStruct {  
   char a;  
   int i;   // C4820  
};  
  
// OK  
#pragma pack(1)  
__declspec(align(1)) struct MyStruct2 {  
   char a;  
   int i;  
};  
```