---
title: "_amsg_exit | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _amsg_exit
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _amsg_exit
dev_langs:
- C++
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b9029cbcfaa3853638a5b46e2c3ee1cb56622cb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="amsgexit"></a>_amsg_exit
지정된 런타임 오류 메시지를 내보낸 다음 오류 코드 255와 함께 응용 프로그램을 종료합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rterrnum`  
 시스템 정의 런타임 오류 메시지의 ID 번호입니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 콘솔 응용 프로그램에 대한 런타임 오류 메시지를 **stderr**로 내보내거나 Windows 응용 프로그램에 대한 메시지를 메시지 상자에 표시합니다. 디버그 모드에서 종료하기 전에 디버거를 호출하도록 선택할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|_amsg_exit|internal.h|