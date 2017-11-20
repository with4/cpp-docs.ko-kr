---
title: "fseek, _lseek 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
dev_langs: C++
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 714a25838c40286fac69fafb88d673e65b1e2f14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="fseek-lseek-constants"></a>fseek, _lseek 상수
## <a name="syntax"></a>구문  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>설명  
 *origin* 인수는 초기 위치를 지정하며 다음 매니페스트 상수 중 하나가 될 수 있습니다.  
  
|상수|의미|  
|--------------|-------------|  
|`SEEK_END`|파일 끝|  
|`SEEK_CUR`|파일 포인터의 현재 위치|  
|`SEEK_SET`|파일 시작 부분|  
  
## <a name="see-also"></a>참고 항목  
 [fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [전역 상수](../c-runtime-library/global-constants.md)