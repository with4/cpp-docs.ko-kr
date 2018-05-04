---
title: . 링커 입력 파일로 ilk 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01fea585b86114373017b6d73948cb1438b7185e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ilk-files-as-linker-input"></a>링커 입력 파일로 사용하는 .Ilk 파일
때.ilk 상태 파일의 첫 번째 증분 링크 중에 만든을 업데이트 합니다. 이 파일에.exe 파일이 나.dll 파일와 동일한 기본 이름이 되었으며 확장.ilk. 후속 증분 링크 하는 동안 링크.ilk 파일을 업데이트 합니다. .Ilk 파일이 없는 경우 링크 전체 링크를 수행 하 고 새.ilk 파일을 만듭니다. .Ilk 파일을 사용할 수 없으면 비증분 링크를 수행 합니다. 증분 링크에 대 한 세부 정보를 참조 하십시오.는 [증분 링크 (/incremental)](../../build/reference/incremental-link-incrementally.md) 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINK 입력된 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)