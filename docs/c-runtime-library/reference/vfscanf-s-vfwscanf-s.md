---
title: vfscanf_s, vfwscanf_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- vfscanf_s
- vfwscanf_s
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
- vfscanf_s
- vfwscanf_s
- _vftscanf_s
dev_langs:
- C++
ms.assetid: 9b0133f0-9a18-4581-b24b-3b72683ad432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79b00ee0216120451c029b7de1caf9ac1967f802
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416313"
---
# <a name="vfscanfs-vfwscanfs"></a>vfscanf_s, vfwscanf_s

스트림에서 형식이 지정된 데이터를 읽습니다. 이러한 버전의 vfscanf, vfwscanf에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
int vfscanf_s(
   FILE *stream,
   const char *format,
   va_list arglist
);
int vfwscanf_s(
   FILE *stream,
   const wchar_t *format,
   va_list arglist
);

```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*format*<br/>
형식 컨트롤 문자열입니다.

*arglist*<br/>
가변 인수 목록입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 모두 성공적으로 변환되고 할당된 필드 수를 반환합니다. 이때 읽혀졌지만 할당되지 않은 필드는 반환 값에 포함되지 않습니다. 반환 값이 0이면 할당된 필드가 없음을 나타냅니다. 오류가 발생 했거나 반환 값은 첫 번째 변환 하기 전에 파일 스트림의 끝에 도달 하는 경우 **EOF** 에 대 한 **vfscanf_s** 및 **vfwscanf_s**합니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 *스트림* 는 잘못 된 파일 포인터 또는 *형식* 가 null 포인터 이면 이러한 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우 이러한 함수가 반환 **EOF** 설정 **errno** 를 **EINVAL**합니다.

## <a name="remarks"></a>설명

**vfscanf_s** 함수의 현재 위치에서 데이터를 읽고 *스트림* 제공 된 위치에는 *arglist* 인수 목록 (있는 경우). 목록의 각 인수의 형식 지정자에 해당 하는 형식의 변수에 대 한 포인터 여야 합니다. *형식*합니다. *형식* 컨트롤 입력의 해석은 필드 및 동일한 형태와 기능을 *형식* 에 대 한 인수 **scanf_s**; 참조 [형식 사양 필드: scanf 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) 에 대 한 설명은 *형식*합니다. **vfwscanf_s** 의 와이드 문자 버전이 **vfscanf_s**; format 인수를 **vfwscanf_s** 는 와이드 문자 문자열입니다. 스트림이 ANSI 모드에서 열리는 경우 이러한 함수는 동일하게 작동합니다. **vfscanf_s** 현재 UNICODE 스트림에서의 입력을 지원 하지 않습니다.

보다 안전한 함수 간의 주요 차이점 (않은 **_s** 접미사) 다른 버전에 더 안전한 함수 필요한 크기는 각 문자는 **c**, **C**, **s**, **S**, 및 **[** 종류 필드를 바로 뒤에 변수를 인수로 전달할 수 있습니다. 자세한 내용은 [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) 및 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)을 참조하세요.

> [!NOTE]
> 크기 매개 변수는 형식 **서명 되지 않은**이 아니라 **size_t**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftscanf_s**|**vfscanf_s**|**vfscanf_s**|**vfwscanf_s**|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**vfscanf_s**|\<stdio.h>|
|**vfwscanf_s**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_vfscanf_s.c
// compile with: /W3
// This program writes formatted
// data to a file. It then uses vfscanf_s to
// read the various data back from the file.

#include <stdio.h>
#include <stdarg.h>
#include <stdlib.h>

FILE *stream;

int call_vfscanf_s(FILE * istream, char * format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vfscanf_s(istream, format, arglist);
    va_end(arglist);
    return result;
}

int main(void)
{
    long l;
    float fp;
    char s[81];
    char c;

    if (fopen_s(&stream, "vfscanf_s.out", "w+") != 0)
    {
        printf("The file vfscanf_s.out was not opened\n");
    }
    else
    {
        fprintf(stream, "%s %ld %f%c", "a-string",
            65000, 3.14159, 'x');
        // Security caution!
        // Beware loading data from a file without confirming its size,
        // as it may lead to a buffer overrun situation.

        // Set pointer to beginning of file:
        fseek(stream, 0L, SEEK_SET);

        // Read data back from file:
        call_vfscanf_s(stream, "%s %ld %f%c", s, _countof(s), &l, &fp, &c, 1);

        // Output data read:
        printf("%s\n", s);
        printf("%ld\n", l);
        printf("%f\n", fp);
        printf("%c\n", c);

        fclose(stream);
    }
}

```

```Output
a-string
65000
3.141590
x
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[vfscanf, vfwscanf](vfscanf-vfwscanf.md)<br/>
