---
title: "경로 필드 제한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs:
- C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e00104ada550d2510b031804d073098693144768
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="path-field-limits"></a>경로 필드 제한
## <a name="syntax"></a>구문  
  
```  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>설명  
 이러한 상수는 경로 및 경로 내 개별 필드의 최대 길이를 정의합니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_MAX_DIR`|디렉터리 구성 요소의 최대 길이입니다.|  
|`_MAX_DRIVE`|드라이브 구성 요소의 최대 길이입니다.|  
|`_MAX_EXT`|확장명 구성 요소의 최대 길이입니다.|  
|`_MAX_FNAME`|파일 이름 구성 요소의 최대 길이입니다.|  
|`_MAX_PATH`|전체 경로의 최대 길이입니다.|  
  
> [!NOTE]
>  C 런타임은 최대 32,768자의 경로 길이를 지원하지만 운영 체제, 특히 파일 시스템에서는 해당 길이보다 긴 경로를 지원합니다. 필드 합계는 FAT32 파일 시스템과의 전체 이전 버전 호환성을 위해 `_MAX_PATH`를 초과할 수 없습니다. [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../atl/reference/includes/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] 및 Windows Vista NTFS 파일 시스템은 유니코드 API를 사용하는 경우에만 최대 32,768자의 경로 길이를 지원합니다. 긴 경로 이름을 사용하는 경우 경로 앞에 \\\\?\ 문자를 붙이고 유니코드 버전의 C 런타임 함수를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)
