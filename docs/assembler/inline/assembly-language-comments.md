---
title: "어셈블리 언어 설명 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee9ab1975a1146b598d7955d15b8e91a0f396724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="assembly-language-comments"></a>어셈블리 언어 설명
## <a name="microsoft-specific"></a>Microsoft 전용  
 `__asm` 블록의 지침에서는 어셈블리 언어 주석을 사용할 수 있습니다.  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 C 매크로가 단일 논리 줄로 확장되기 때문에 매크로에서 어셈블리 언어 주석을 사용하지 마십시오. (참조 [C 매크로로 __asm 블록 정의](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) `__asm` 블록 수도 C-스타일 주석도 포함할; 자세한 내용은 참조 [C를 사용 하 여 또는 __asm 블록에서 c + +](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)