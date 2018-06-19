---
title: -REBASE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rebase
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a5e2b68768b01d71532c358a14c53d8a033e1ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377091"
---
# <a name="rebase"></a>/다시 지정
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>설명  
 이 옵션의 기본 주소를 지정된 된 파일을 설정합니다. EDITBIN 가장 가까운 64 KB로 반올림 각 파일의 크기에 따라 연속적인 주소 공간에 새 기본 주소를 할당 합니다. 기본 주소에 대 한 세부 정보를 참조 하십시오.는 [기준 주소](../../build/reference/base-base-address.md) (/base) 링커 옵션입니다.  
  
 프로그램의 실행 파일과 Dll에 지정 된 *파일* EDITBIN 명령줄을 사용 하려면 되는 순서에서에 인수입니다. 하나 이상의 선택적으로 지정할 수 *한정자*쉼표로 구분 하는, (**,**):  
  
|한정자|작업|  
|--------------|------------|  
|기본 **= * * * 주소*|파일에 기본 주소를 다시 할당 하기 위해 시작 주소를 제공 합니다. 지정 *주소* 10 진수 또는 C 언어 표기법입니다. BASE를 지정 하지 않은 경우 기본적으로 시작 하는 기본 주소는 0x400000입니다. DOWN이 사용 되는, 기본 사람은 및 *주소* 의 기본 주소 범위의 끝을 설정 합니다.|  
|BASEFILE|COFFBASE 라는 파일을 만듭니다. TXT 옵션 /base는 링크의 필요한 형식에 있는 텍스트 파일입니다.|  
|아래로|끝 주소에서 아래쪽으로 기준 주소 다시 할당 하도록 EDITBIN 지시 합니다. 파일은 가능한 가장 높은 주소 주소 범위의 끝 부분 아래에 있는 첫 번째 파일이 지정 된 순서로 다시 할당 됩니다. BASE는 아래쪽에 있는 파일의 기준에 대 한 충분 한 주소 공간을 위해 사용 해야 합니다. 지정된 된 파일에 필요한 주소 공간을 확인 하려면 /REBASE EDITBIN 파일에 대해 실행 하 고 표시 된 전체 크기를 64KB를 추가 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)