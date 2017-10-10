---
title: "심각한 오류 C1060 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 36abe3a63515dcb3b8f07ce5d0d169329ed5f7ab
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1060"></a>심각한 오류 C1060
컴파일러의 힙 공간이 부족합니다.  
  
 운영 체제 또는 런타임 라이브러리가 메모리 요청을 처리할 수 없습니다.  
  
### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>이 오류를 해결하려면 다음 해결 방법을 시도해 보세요.  
  
1.  컴파일러 오류도 발생 하는 경우 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) 및 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)를 사용 하 여는 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) 컴파일러 옵션을 사용 하 여 메모리 할당 제한을 낮춥니다. 남은 메모리 할당을 낮추면 응용 프로그램에 더 많은 힙 공간을 사용할 수 있습니다.  
  
     경우는 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) 옵션이 이미 설정 되어, 제거해 봅니다. 옵션에 지정된 메모리 할당 제한이 너무 높으면 힙 공간이 모두 사용되었을 수 있습니다. 컴파일러 기본 제한을 사용 하 여 제거 하는 경우는 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) 옵션입니다.  
  
2.  64비트 플랫폼에서 컴파일하는 경우 64비트 컴파일러 도구 집합을 사용합니다. 자세한 내용은 참조 [하는 방법: 명령줄에서 64 비트 Visual c + + 도구를 사용 하도록 설정](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)합니다.  
  
3.  32 비트 Windows에서 사용 하 여 시도 [3GB](http://go.microsoft.com/fwlink/?LinkId=177831) boot.ini 스위치가 있습니다.  
  
4.  Windows 스왑 파일의 크기를 늘립니다.  
  
5.  실행 중인 다른 프로그램을 닫습니다.  
  
6.  필요 없는 포함 파일을 제거합니다.  
  
7.  예를 들어 대형 배열을 선언하는 대신에 메모리를 동적으로 할당하여 필요 없는 전역 변수를 제거합니다.  
  
8.  사용되지 않는 선언을 제거합니다.  
  
9. 현재 파일을 좀 더 작은 여러 개의 파일로 분할합니다.
