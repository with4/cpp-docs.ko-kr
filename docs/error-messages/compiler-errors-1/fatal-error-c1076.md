---
title: "심각한 오류 C1076 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1076
dev_langs:
- C++
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 617db809cfaeb4d0e0003a3dfc2e9568726b0c58
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1076"></a>심각한 오류 C1076
컴파일러 한계 : 내부 힙 한계에 도달했습니다. /Zm을 사용하여 한계를 더 높게 지정하십시오.  
  
 템플릿 인스턴스화나 기호가 너무 많은 경우 이 오류가 발생할 수 있습니다.  
  
 이 오류를 해결하려면  
  
1.  사용 하 여는 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) 컴파일러 메모리 제한을에 지정 된 값으로 설정 하는 옵션은 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) 오류 메시지입니다. 이 값을 설정 하는 방법을 포함 하는 자세한 정보에 대 한 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)], 주의 섹션을 참조 [/Zm (지정 미리 컴파일된 헤더 메모리 할당 제한)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)합니다.  
  
2.  64비트 운영 체제에서 32비트로 호스팅된 컴파일러를 사용하는 경우 64비트로 호스팅된 컴파일러를 대신 사용하십시오. 자세한 내용은 참조 [하는 방법: 명령줄에서 64 비트 Visual c + + 도구를 사용 하도록 설정](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)합니다.  
  
3.  필요 없는 포함 파일을 제거합니다.  
  
4.  예를 들어, 대형 배열을 선언하는 대신에 메모리를 동적으로 할당하여 필요 없는 전역 변수를 제거합니다.  
  
5.  사용되지 않는 선언을 제거합니다.  
  
6.  대형 함수를 좀 더 작은 함수로 분할합니다.  
  
7.  대형 클래스를 좀 더 작은 클래스로 분할합니다.  
  
8.  현재 파일을 좀 더 작은 여러 개의 파일로 분할합니다.  
  
 값에 대해 지정 된 빌드가 시작 된 후 바로 c 1076이 발생 하면 **/Zm** 너무 높기 때문일 프로그램에 대 한 합니다. 줄이기는 **/Zm** 값입니다.