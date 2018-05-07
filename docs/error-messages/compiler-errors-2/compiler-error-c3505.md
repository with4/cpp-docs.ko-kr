---
title: 컴파일러 오류 C3505 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3505
dev_langs:
- C++
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e0ea8edd3237db2085365450f43b4b955d36f33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3505"></a>컴파일러 오류 C3505

> 형식 라이브러리를 로드할 수 없습니다 '*guid*'  
  
C3505는 32 비트, x86 호스트 크로스 컴파일러 64 비트를 실행 하는 경우 발생할 수 있습니다, 그리고 32 비트 레지스트리 하이브에에서 읽을 x64 64 비트 컴파일러는 w o w 64에서 실행 되 고은 컴퓨터 대상과 수 있습니다.  
  
32 비트 및 64 비트 버전을 가져오려면 하려고 하는 형식 라이브러리의를 구축 하 여이 오류를 해결 하 고 모두를 등록할 수 있습니다.  변경 해야 하는 네이티브 64 비트 컴파일러를 사용할 수 있습니다 프로그램 **VC + + 디렉터리** 64 비트 컴파일러를 가리키도록 IDE에서 속성입니다.  
  
자세한 내용은 다음 항목을 참조하세요.  
  
-   [방법: 명령줄에서 64비트 Visual C++ 도구 집합 사용](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [방법: 64비트, x64 플랫폼을 대상으로 한 Visual C++ 프로젝트 구성](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)