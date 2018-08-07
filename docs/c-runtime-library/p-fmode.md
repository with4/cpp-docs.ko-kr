---
title: __p__fmode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- __p__fmode
dev_langs:
- C++
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c520f81062f1bbbb295f17c6bc041afb8b5f2877
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389838"
---
# <a name="pfmode"></a>__p__fmode
파일 I/O 연산에 대한 기본 *파일 변환 모드*를 지정하는 `_fmode` 전역 변수에 대한 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## <a name="return-value"></a>반환 값  
 `_fmode` 전역 변수에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `__p__fmode` 함수는 내부용이며 사용자 코드에서 호출할 수 없습니다.  
  
 파일 변환 모드는 [_open](../c-runtime-library/reference/open-wopen.md) 및 [_pipe](../c-runtime-library/reference/pipe.md) I/O 연산에 대한 `binary` 또는 `text` 변환을 지정합니다. 자세한 내용은 [_fmode](../c-runtime-library/fmode.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|__p\__fmode|stdlib.h|