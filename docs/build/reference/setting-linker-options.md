---
title: "링커 옵션 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b64b1dfd342598735124940d01b1bb4939242e10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="setting-linker-options"></a>링커 옵션 설정
내부 또는 개발 환경 외부에서 링커 옵션을 설정할 수 있습니다. 각 링커 옵션에 대 한 알아봅니다 방법을 개발 환경에서 설정할 수 있습니다. 참조 [링커 옵션](../../build/reference/linker-options.md) 전체 목록은 합니다.  
  
 개발 환경 외부 링크를 실행 하는 경우에 하나 이상의 방법으로 입력을 지정할 수 있습니다.  
  
-   에 [명령줄](../../build/reference/linker-command-line-syntax.md)  
  
-   사용 하 여 [명령 파일](../../build/reference/link-command-files.md)  
  
-   [환경 변수](../../build/reference/link-environment-variables.md)  
  
 링크 환경 변수에 지정 된 링크의 첫 번째 프로세스 옵션 뒤에 명령 파일 및 명령줄에 지정 된 순서 대로 옵션입니다. 경우 옵션 다른 인수와 함께 반복 되는 마지막 처리 우선 합니다.  
  
 옵션은 전체 빌드;에 적용 옵션 없이 특정 입력된 파일에 적용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C/C++ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [링커 옵션](../../build/reference/linker-options.md)