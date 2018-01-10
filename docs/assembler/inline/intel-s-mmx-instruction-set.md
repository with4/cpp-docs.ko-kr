---
title: "Intel &#39; s MMX 명령 집합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MMX instruction set
ms.assetid: 705deb2d-c3fd-4696-9e22-8bcf25866daf
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b8aa4dc38a8ed04c2df04eaa944d43769ae996f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="intel39s-mmx-instruction-set"></a>Intel &#39; s MMX 명령 집합
## <a name="microsoft-specific"></a>Microsoft 전용  
 Visual C++ 컴파일러는 인라인 어셈블러에서 Intel의 MMX(멀티미디어 확장명) 명령 집합을 사용할 수 있도록 해 줍니다. 또한 MMX 명령은 디버거의 디스어셈블리에서 지원됩니다. 컴파일러는 함수에 MMX 명령이 포함되어 있지만 멀티미디어 상태를 비우는 EMMS 명령이 포함되어 있지 않은 경우 경고 메시지를 생성합니다. 자세한 내용은 Intel 웹 사이트를 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)