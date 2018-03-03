---
title: "링커 도구 경고 LNK4078 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4078
dev_langs:
- C++
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8109ef98237f545a2139be8f0502acd11407314b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4078"></a>링커 도구 경고 LNK4078
여러 '섹션 이름' 섹션이 다양 한 특성  
  
 링크 두 개를 찾거나 이름은 하지만 서로 다른 특성이 동일한 이상의 섹션.  
  
 이전 버전의 링크 또는 LIB에 의해 생성 된 가져오기 라이브러리 또는 내보내기 파일에서이 경고를 발생할 수 있습니다.  
  
 파일 및 다시 연결을 다시 만듭니다.  
  
## <a name="example"></a>예  
 주요 변경 내용으로 LNK4078 발생할 수도 있습니다: 된 [init_seg](../../preprocessor/init-seg.md) x86 았으 읽기/쓰기, 이제 읽기 전용입니다.  
  
 다음 샘플에서는 LNK4078 합니다.  
  
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