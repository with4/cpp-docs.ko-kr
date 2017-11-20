---
title: "LINK 명령 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2b6543cbb54dc982b1e55be8c0c554a429410b78
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="link-command-files"></a>LINK 명령 파일
명령 파일 형식으로의 링크를 명령줄 인수를 전달할 수 있습니다. 링커에 명령 파일을 지정 하려면 다음 구문을 사용 합니다.  
  
```  
LINK @commandfile  
```  
  
 `commandfile` 텍스트 파일의 이름입니다. 없습니다 공백 또는 탭 간 허용 되는 at 기호 (@) 및 파일 이름입니다. 기본 확장명이 없습니다. 전체 파일 이름 확장명을 포함 하 여 지정 해야 합니다. 와일드 카드를 사용할 수 없습니다. 파일 이름으로 절대 또는 상대 경로 지정할 수 있습니다. 링크 파일을 검색 하는 환경 변수를 사용 하지 않습니다.  
  
 명령 파일의 인수를 분리할 공백이 나 탭으로 (처럼 명령줄에서) 또는 줄 바꿈 문자로 하 고 있습니다.  
  
 명령 파일의 명령줄의 전체 또는 일부를 지정할 수 있습니다. LINK 명령의 명령 파일을 여러 개 사용할 수 있습니다. 링크는 명령줄에 해당 위치에 지정 된 것 처럼 명령 파일 입력을 받아들입니다. 명령 파일을 중첩할 수 없습니다. 링크 하지 않는 한 명령 파일의 내용을 에코는 [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md) 옵션을 지정 합니다.  
  
## <a name="example"></a>예제  
 Dll을 다음 명령을 명령 파일에 있는 개체 파일 및 라이브러리의 이름을 전달 하 고 사용 하 여 세 번째 명령 /EXPORTS 옵션의 파일:  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)