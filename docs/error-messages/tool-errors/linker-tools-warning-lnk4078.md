---
title: "링커 도구 경고 LNK4078 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4078"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4078"
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 링커 도구 경고 LNK4078
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여러 'section name' 섹션이 다양한 특성을 갖고 있습니다.  
  
 LINK가 이름은 같지만 특성이 다른 둘 이상의 섹션을 발견했습니다.  
  
 이 경고는 가져오기 라이브러리 또는 내보내기 파일이 이전 버전의 LINK 또는 LIB에 의해 만들어진 경우에 발생할 수 있습니다.  
  
 파일을 다시 만들어서 다시 링크하십시오.  
  
## 예제  
 LNK4078은 변경된 기본 동작으로 인해 발생할 수도 있습니다. x86에서는 [init\_seg](../../preprocessor/init-seg.md)라는 섹션을 읽고 쓸 수 있었지만 이제는 이 섹션을 읽을 수만 있습니다.  
  
 다음 샘플에서는 LNK4078 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4078.cpp  
// compile with: /W1  
// LNK4078 expected  
#include <stdio.h>  
#pragma warning(disable : 4075)  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors to call  
PF pfx[200];   // pointers to destructors.  
  
struct A { A() {} };  
  
int myexit (PF pf) { return 0; }  
  
#pragma section(".mine$a", read, write)  
// try the following line instead  
// #pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) int ii = 1;  
  
#pragma section(".mine$z", read, write)  
// try the following line instead  
// #pragma section(".mine$z", read)  
__declspec(allocate(".mine$z")) int i = 1;  
  
#pragma data_seg()  
#pragma init_seg(".mine$m", myexit)  
A bbbb;   
A cccc;  
int main() {}  
```