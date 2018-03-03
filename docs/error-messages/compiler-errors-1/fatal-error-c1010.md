---
title: "심각한 오류 C1010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1010
dev_langs:
- C++
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b2123118be2a8a382f6b718499c5af16f88d111
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1010"></a>심각한 오류 C1010
미리 컴파일된 헤더를 찾는 동안 예기치 않은 파일의 끝이 나타났습니다. 추가 하 였는 ' #include 이름 ' 소스에?  
  
 지정 된 include 파일 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) 소스 파일에 나열 되지 않은 합니다.  대부분의 Visual c + + 프로젝트 형식에서 기본적으로이 옵션은 및 "stdafx.h"는이 옵션으로 지정 된 파일을 포함 하는 기본값입니다.  
  
 Visual Studio 환경에서이 오류를 해결 하려면 다음 방법 중 하나를 사용 합니다.  
  
-   프로젝트에서 미리 컴파일된 헤더를 사용 하지 않는 경우 설정의 **미리 컴파일된 헤더 만들기/사용** 에 소스 파일의 속성 **하지 미리 컴파일된 헤더를 사용 하 여**합니다. 이 컴파일러 옵션을 설정 하려면 다음이 단계를 수행 합니다.  
  
    1.  프로젝트의 솔루션 탐색기 창에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.  
  
    2.  왼쪽된 창에서 클릭 된 **C/c + +** 폴더입니다.  
  
    3.  클릭는 **미리 컴파일된 헤더** 노드.  
  
    4.  오른쪽 창에서 클릭 **미리 컴파일된 헤더 만들기/사용**, 클릭 하 고 **미리 컴파일된 헤더 사용 안 함**합니다.  
  
-   잘못 삭제, 바꾸었거나 헤더 파일을 제거 되었는지 확인 (기본적으로 stdafx.h) 현재 프로젝트에서. 이 파일은 또한 사용 하 여 소스 파일의 다른 코드 보다 먼저 포함 될 필요 **#include "stdafx.h"**합니다. (으로이 헤더 파일을 지정 **파일에서 PCH 만들기/사용** 프로젝트 속성)