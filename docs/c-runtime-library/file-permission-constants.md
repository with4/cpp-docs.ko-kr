---
title: "파일 사용 권한 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs:
- C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: 6
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
ms.openlocfilehash: fe25cc1ce973d46c87425b59cc2da3544b216033
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="file-permission-constants"></a>파일 사용 권한 상수
## <a name="syntax"></a>구문  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## <a name="remarks"></a>설명  
 `_O_CREAT`(`_open`, `_sopen`)가 지정되었을 때 이러한 상수 중 하나가 필요합니다.  
  
 `pmode` 인수는 파일의 사용 권한 설정을 다음과 같이 지정합니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_S_IREAD`|읽기 허용|  
|`_S_IWRITE`|쓰기 허용|  
|`_S_IREAD` &#124; `_S_IWRITE`|읽기 및 쓰기 허용|  
  
 `pmode` 인수를 `_umask`에 대해 사용하는 경우 매니페스트 상수는 다음과 같이 권한을 설정합니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_S_IREAD`|쓰기가 허용되지 않음(읽기 전용)|  
|`_S_IWRITE`|읽기가 허용되지 않음(쓰기 전용)|  
|`_S_IREAD` &#124; `_S_IWRITE`|읽기나 쓰기 모두 허용되지 않음|  
  
## <a name="see-also"></a>참고 항목  
 [_open, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../c-runtime-library/reference/umask.md)   
 [표준 형식](../c-runtime-library/standard-types.md)   
 [전역 상수](../c-runtime-library/global-constants.md)
