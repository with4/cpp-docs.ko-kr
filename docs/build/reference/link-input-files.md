---
title: "입력 파일 링크 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d0cae9498d2c9b49e52cf56991d2425de39d7e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="link-input-files"></a>LINK 입력 파일
개체, 가져오기 및 표준 라이브러리, 리소스, 모듈 정 및 명령 입력을 포함 하는 파일에 링커를 제공 합니다. 링크 파일의 내용에 대해 정도 파일 확장명을 사용 하지 않습니다. 대신, 링크는 어떤 종류의 파일 인지 확인 하려면 각 입력된 파일을 검사 합니다.  
  
 명령줄에서 개체 파일은 명령줄에서 순서 대로 처리 됩니다. 다음 다 경고와 함께 라이브러리도 순서 명령줄에서에서 검색 됩니다: 때 개체 파일을 라이브러리에서 가져올 수 있으므로 검색에 대 한 해당 라이브러리에 먼저 및 고명령줄에서다음라이브러리기호를확인할수없는[/DEFAULTLIB (기본 라이브러리 지정)](../../build/reference/defaultlib-specify-default-library.md) 지시문, 한 다음 명령줄의 시작 부분에서 모든 라이브러리입니다.  
  
> [!NOTE]
>  링크는 더 이상 응답 파일 및 순서 파일에 주석의 시작으로 세미콜론 (또는 다른 문자)를 받아들입니다. 세미콜론 모듈 정의 파일 (.def) 주석의 시작 으로만 인식 됩니다.  
  
 링크는 다음과 같은 유형의 입력된 파일을 사용합니다.  
  
-   [.obj 파일](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [.netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [.lib 파일](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [.exp 파일](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [.def 파일](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [.pdb 파일](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [.res 파일](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [.exe 파일](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [.txt 파일](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [.ilk 파일](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)