---
title: "_fmode | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fmode
- _fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 3c0946419e1c0a408a7dfad190387f0165d9fba0
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="fmode"></a>_fmode
`_fmode` 변수는 텍스트 또는 이진 변환에 대한 기본 파일 변환 모드를 설정합니다. 이 전역 변수는 전역 변수 대신 사용되어야 할 보안 기능이 보다 강화된 버전인 [_get_fmode](../c-runtime-library/reference/get-fmode.md) 및 [_set_fmode](../c-runtime-library/reference/set-fmode.md)에 대해서는 더 이상 사용되지 않습니다. 이 변수는 Stdlib.h에 다음과 같이 선언됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
extern int _fmode;  
```  
  
## <a name="remarks"></a>설명  
 텍스트 모드 변환의 경우 `_fmode`의 기본 설정은 `_O_TEXT`입니다. 이진 모드에 대한 설정은 `_O_BINARY`입니다.  
  
 다음과 같은 세 가지 방법으로 `_fmode` 값을 변경할 수 있습니다.  
  
-   Binmode.obj와 연결합니다. 그러면 `_fmode`의 초기 설정이 `_O_BINARY`로 변경되어 `stdin`, `stdout` 및 `stderr`를 제외한 모든 파일이 이진 모드에서 열립니다.  
  
-   `_get_fmode` 또는 `_set_fmode`를 호출하여 각각 `_fmode` 전역 변수를 가져오거나 설정합니다.  
  
-   프로그램에서 `_fmode` 값을 설정하여 직접 값을 변경합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전역 변수](../c-runtime-library/global-variables.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)
