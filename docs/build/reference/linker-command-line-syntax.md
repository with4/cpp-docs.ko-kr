---
title: 링커 명령줄 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], syntax
- linker command line [C++]
- LINK tool [C++], command-line syntax
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd5b1b809bfbbb01bca91f3677774d396515f56e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="linker-command-line-syntax"></a>링커 명령줄 구문
링크를 실행 합니다. EXE를 다음 명령 구문을 사용 합니다.  
  
```  
LINK arguments  
```  
  
 `arguments` 옵션과 파일 이름이 포함 및 순서에 관계 없이 지정할 수 있습니다. 처리 된 가장 먼저 다음 파일은 옵션입니다. 하나 이상의 공백이 나 탭을 사용 하 여 인수를 구분 합니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
 명령줄 옵션은 옵션 지정자 이루어집니다 대시 (-) 또는 슬래시 (/) 옵션의 이름이 차례로 나옵니다. 옵션 이름은 축약 될 수 없습니다. 일부 옵션이 콜론 (:) 다음에 지정 된 인수를 사용 합니다. 공백 또는 탭 옵션 사양에를 제외한 허용 되지 /COMMENT 옵션에 따옴표로 묶은 문자열입니다. 10 진수 또는 C 언어 표기법에서 숫자 인수를 지정 합니다. 옵션 이름 및 키워드 또는 파일 이름 인수는 대/소문자를 구분 하지 않는 식별자 인수로 대/소문자 구분.  
  
 파일을 링커로 전달 하려면 링크 명령 실행 후 명령줄에서 파일 이름을 지정 합니다. 절대 또는 상대 경로 파일 이름으로 지정할 수 있습니다 및 파일 이름에 와일드 카드를 사용할 수 있습니다. 점 (.) 및 파일 이름 확장명을 생략 하면 링크.obj 파일을 찾기 위해 가정 합니다. 링크 또는 사용 하지 않는 파일 이름 확장명의 부족을 통해 파일의 내용에 대해 가정 검사 하 여 파일의 형식을 결정 하 고 적절 하 게 처리 합니다.  
  
 link.exe는 성공 (오류 없음)에 0을 반환합니다.  그렇지 않은 경우 링커는 링크 중지 된 오류 번호를 반환 합니다.  예를 들어 링커 LNK1104를 생성 하는 경우 링커 1104를 반환 합니다.  따라서 가장 낮은 링커에서 오류 발생 시 반환 된 오류 번호는 1000입니다.  반환 값이 128 운영 체제 또는;.config 파일에 구성 문제가 나타냅니다. 로더는 link.exe 또는 c2.dll 로드 하지 못했습니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)