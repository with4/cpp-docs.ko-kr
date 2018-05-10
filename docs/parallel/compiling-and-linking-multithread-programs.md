---
title: 컴파일 및 다중 스레드 프로그램 링크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c77cb217fe841e15f4c7470340bd3fbb502f6a9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="compiling-and-linking-multithread-programs"></a>다중 스레드 프로그램 컴파일 및 링크
에 도입 된 Bounce.c 프로그램 [샘플 다중 스레드 C 프로그램](../parallel/sample-multithread-c-program.md)합니다.  
  
 프로그램은 컴파일된 기본적으로 다중 스레드입니다.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>컴파일하고 연결 개발 환경 내에서 Bounce.c 다중 스레드 프로그램  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  에 **프로젝트 형식** 창에서 클릭 **Win32**합니다.  
  
3.  에 **템플릿** 창에서 클릭 **Win32 콘솔 응용 프로그램**, 프로젝트 이름을 지정 합니다.  
  
4.  프로젝트에 C 소스 코드를 포함 하는 파일을 추가 합니다.  
  
5.  에 **빌드** 메뉴를 클릭 하 여 프로젝트를 빌드합니다는 **빌드** 명령입니다.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>컴파일하고 연결 Bounce.c 명령줄에서 다중 스레드 프로그램  
  
1.  컴파일 및 프로그램을 링크 합니다.  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [C 및 Win32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)