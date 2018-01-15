---
title: "Include 파일에서의 다중 스레딩과 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f71b52bca5f636d80f2d55cc5e9ffc3e217d90a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="include-files-for-multithreading"></a>다중 스레딩을 위한 포함 파일
표준 포함 파일은 라이브러리에서 구현 된 대로 C 런타임 라이브러리 함수를 선언 합니다. 사용 하는 경우는 [최대 최적화](../build/reference/ox-full-optimization.md) (/ Ox) 또는 [fastcall 호출 규칙](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) 옵션을 컴파일러 간주 레지스터 호출 규칙을 사용 하 여 모든 함수 호출 수입니다. 런타임 라이브러리 함수가 C 호출 규칙을 사용 하 여 컴파일된 및 표준 포함 파일의 선언을 이러한 함수에 대 한 올바른 외부 참조를 생성 하도록 컴파일러에 지시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 및 Win32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)