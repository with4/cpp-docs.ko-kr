---
title: _open_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _open_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
dev_langs: C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff05c99180ff8933316e1db9366da3b985c10305
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="openosfhandle"></a>_open_osfhandle

C 런타임 파일 설명자를 기존 운영 체제 파일 핸들에 연결합니다.

## <a name="syntax"></a>구문

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>매개 변수

*osfhandle*  
운영 체제 파일 핸들입니다.

*flags*  
허용되는 연산의 유형입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되면 `_open_osfhandle`은 C 런타임 파일 설명자를 반환합니다. 그렇지 않으면-1을 반환 합니다.

## <a name="remarks"></a>설명

`_open_osfhandle` 함수 C 런타임 파일 설명자를 할당 하 고 지정 된 운영 체제 파일 핸들에 연결 *osfhandle*합니다. *플래그* 인수가 Fcntl.h에 정의 된 매니페스트 상수 중 하나 이상을에서 형성 하는 정수 식입니다. 매니페스트 상수를 두 개 이상의 형식으로 사용 하는 경우는 *플래그* 인수를 해당 상수는 비트 OR 연산자로 결합 됩니다 ( **&#124;** ).

Fcntl.h 다음 매니페스트 상수를 정의합니다.

**\_O\_추가**  
모든 쓰기 작업 전에 파일 포인터를 파일 끝에 배치합니다.

**\_O\_RDONLY**  
읽기 전용으로 파일을 엽니다.

**\_O\_텍스트**  
파일을 텍스트(변환됨) 모드에서 엽니다.

**\_O\_WTEXT**  
파일을 유니코드(변환된 UTF-16) 모드에서 엽니다.

사용 하 여 열린 파일을 닫으려면 `_open_osfhandle`, 호출 [ \_닫습니다](../../c-runtime-library/reference/close.md)합니다. 호출 하 여 기본 OS 파일 핸들도 닫혀 `_close`Win32 함수를 호출 하는 데 필요한 이므로, `CloseHandle` 원래 핸들에 합니다. 파일 설명자가 소유 하는 경우는 `FILE *` 다음 호출 하는 스트림 [fclose](../../c-runtime-library/reference/fclose-fcloseall.md) 그에 `FILE *` 스트림의 파일 설명자와 기본 핸들도 닫힙니다. 이 경우 호출 하지 마십시오 `_close` 파일 설명자에 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`_open_osfhandle`|\<io.h>|

호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)  
