---
title: ML 및 ML64 명령줄 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ML
dev_langs:
- C++
helpviewer_keywords:
- /W* MASM compiler option
- /c MASM compiler option
- /EP MASM compiler option
- /Fe MASM compiler option
- /Zp MASM compiler option
- /AT MASM compiler option
- /Zm MASM compiler option
- /Sf MASM compiler option
- /Sp MASM compiler option
- /w MASM compiler option
- /Fl MASM compiler option
- /coff MASM compiler option
- /St MASM compiler option
- /Cx MASM compiler option
- /Sl MASM compiler option
- /Cu MASM compiler option
- MASM (Microsoft Macro Assembler), ML command-line reference
- /FPi MASM compiler option
- /Zf MASM compiler option
- ML environment variable
- /Fr MASM compiler option
- /help MASM compiler option
- /Sa MASM compiler option
- /Zd MASM compiler option
- /I MASM compiler option
- /? MASM compiler option
- /Bl MASM compiler option
- /Fm MASM compiler option
- /Fo MASM compiler option
- command-line reference [ML]
- /Sn MASM compiler option
- /Gd MASM compiler option
- /D* MASM compiler option
- environment variables, ML
- /Gc MASM compiler option
- /F* MASM compiler option
- /Sc MASM compiler option
- /H MASM compiler option
- /Zs MASM compiler option
- /omf MASM compiler option
- /Sg MASM compiler option
- /Cp MASM compiler option
- /Zi MASM compiler option
- /nologo MASM compiler option
- /Sx MASM compiler option
- /WX MASM compiler option
- /Ss MASM compiler option
- command line, reference [ML]
- /Ta MASM compiler option
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da3fb143aeaaf6fa8cf31c45b31707fa01bf6898
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057801"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML 및 ML64 명령줄 참조
조합 하 고 하나 이상의 어셈블리 언어 소스 파일을 연결 합니다. 명령줄 옵션은 대/소문자를 구분 합니다.  
  
 Ml64.exe에 대 한 자세한 내용은 참조 하십시오. [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `options`  
 다음 표에 나열 된 옵션입니다.  
  
|옵션|작업|  
|------------|------------|  
|**/AT**|아주 작은 모델 메모리 지원을 사용합니다. .Com 서식 파일에 대 한 요구 사항을 위반 하는 코드 구문에 대 한 오류 메시지를 사용 하도록 설정 합니다. 이와 동일 하지는 [합니다. 모델](../../assembler/masm/dot-model.md) **아주 작음** 지시문입니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Bl** `filename`|대체 링커를 선택합니다.|  
|**/c**|만 어셈블합니다. 연결 되지 않습니다.|  
|**/coff**|일반적인 개체 파일 COFF (형식) 유형의 개체 모듈을 생성합니다. Win32 어셈블리 언어 개발에는 일반적으로 필요 합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Cp**|모든 사용자 식별자의 대/소문자를 유지합니다.|  
|**/Cu**|모든 식별자가 대문자로 표시 합니다 (기본값)에 매핑됩니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Cx**|공용 및 extern 기호에 대/소문자를 유지합니다.|  
|**/D** `symbol`[[=`value`]]|지정 된 이름의 텍스트 매크로 정의합니다. 경우 `value` 가 누락 된 경우에 비어 있습니다. 공백으로 구분 하 여 여러 토큰 따옴표로 묶어야 합니다.|  
|**/EP**|전처리 원본 목록 (STDOUT으로 전송)을 생성 합니다. 참조 **/Sf**합니다.|  
|**/ERRORREPORT** [ **NONE** &AMP;#124; **프롬프트** &AMP;#124; **큐** &AMP;#124; **보낼** ]|사용할 수 있습니다 ml.exe 또는 ml64.exe 실패 하면 런타임 시 **/ERRORREPORT** 이러한 내부 오류에 대 한 정보를 Microsoft로 보내도록 합니다.<br /><br /> 에 대 한 자세한 내용은 **/ERRORREPORT**, 참조 [/errorReport (내부 컴파일러 오류 보고)](../../build/reference/errorreport-report-internal-compiler-errors.md)합니다.|  
|**/F** `hexnum`|스택 크기를 설정 `hexnum` 바이트 (이와 동일 하 게 **/링크/스택**:`number`). 값은 16 진수 표기법으로 표시 되어야 합니다. 사이 공백이 있어야 **/F** 및 `hexnum`합니다.|  
|**/Fe** `filename`|실행 파일을 이름을 지정 합니다.|  
|**/Fl**[[`filename`]]|어셈블된 코드 목록을 생성합니다. 참조 **/Sf**합니다.|  
|**/Fm**[[`filename`]]|링커 맵 파일을 만듭니다.|  
|**/Fo** `filename`|개체 파일을 이름을 지정 합니다. 자세한 내용은 설명 섹션을 참조 하십시오.|  
|**/FPi**|부동 소수점 연산 (혼합된 언어에만 해당)에 대해 에뮬레이터 픽스업 생성합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Fr**[[`filename`]]|소스 브라우저.sbr 파일을 생성합니다.|  
|**/FR**[[`filename`]]|소스 브라우저.sbr 파일의 확장된 된 형태를 생성합니다.|  
|**/Gc**|포트란 또는 파스칼 스타일 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다. 와 동일 **옵션 언어: 파스칼**합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Gd**|C 스타일 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다. 와 동일 **옵션 언어: C**합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/GZ**|__Stdcall 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다.  와 동일 **옵션 언어: STCALL**합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/H** `number`|외부 이름을 중요 한 문자 수를 제한합니다. 기본값은 31 자 합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/help**|기계 학습에 대 한 도움말 QuickHelp를 호출합니다.|  
|**/I** `pathname`|포함 파일에 대 한 경로 설정 합니다. 10 개 사이로 **/I** 옵션을 사용할 수 있습니다.|  
|**/nologo**|성공적으로 어셈블리에 대 한 메시지를 표시 하지 않습니다.|  
|**/omf**|개체 모듈의 모듈 파일 (OMF 형식) 유형 개체를 생성합니다.  **/omf** 의미 **/c**; ML.exe는 OMF 개체를 연결 하는 것을 지원 하지 않습니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Sa**|사용 가능한 모든 정보 목록이 설정합니다.|  
|**/safeseh**|예외 처리기가 없는 포함 된 또는 사용 하 여 선언 하는 예외 처리기 포함 된 개체 표시 [합니다. SAFESEH](../../assembler/masm/dot-safeseh.md)합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Sf**|첫 번째 단계 목록에 목록 파일을 추가합니다.|  
|**/Sl** `width`|소스 줄에 하나씩 문자에서 목록의 선 두께 설정 합니다. 범위는 60 ~ 255 자의 또는 0입니다. 기본값은 0입니다. 와 동일 [페이지](../../assembler/masm/page.md) 너비입니다.|  
|**/Sn**|목록을 생성 하는 경우 기호 테이블을 끕니다.|  
|**/Sp** `length`|페이지당 줄에 나열 된 원본 페이지 길이 가져오거나 설정 합니다. 범위는 10 ~ 255 자의 또는 0입니다. 기본값은 0입니다. 와 동일 [페이지](../../assembler/masm/page.md) 길이입니다.|  
|**/Ss** `text`|소스 목록에 대 한 텍스트를 지정합니다. 와 동일 [부제목](../../assembler/masm/subtitle.md) 텍스트입니다.|  
|**/St** `text`|소스 목록에 대 한 제목을 지정합니다. 와 동일 [제목](../../assembler/masm/title.md) 텍스트입니다.|  
|**/Sx**|목록에서 false 조건을 설정합니다.|  
|**/Ta** `filename`|소스 파일을 이름이.asm 확장명으로 끝나지 않습니다 어셈블합니다.|  
|**/w**|와 동일 **/W0/WX**합니다.|  
|**/W** `level`|경고 수준을 설정 합니다. 여기서 `level` = 0, 1, 2 또는 3입니다.|  
|**/WX**|경고가 생성 되는 경우 오류 코드를 반환 합니다.|  
|**/X**|INCLUDE 환경 경로 무시 합니다.|  
|**/Zd**|개체 파일에 줄 번호 정보를 생성합니다.|  
|**/Zf**|공용 모든 기호를 만듭니다.|  
|**/Zi**|개체 파일의 CodeView 정보를 생성합니다.|  
|**/Zm**|수 있도록**M510** MASM 5.1과의 호환성이 최대화에 대 한 옵션입니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|  
|**/Zp**[[`alignment`]]|지정 된 바이트 경계에서 구조체를 압축 합니다. `alignment` 1, 2 또는 4 일 수 있습니다.|  
|**/Zs**|구문 검사만을 수행합니다.|  
|**/?**|ML 명령줄 구문에 대 한 요약을 표시합니다.|  
  
 `filename`  
 파일의 이름입니다.  
  
 `linkoptions`  
 링크 옵션입니다.  참조 [링커 옵션](../../build/reference/linker-options.md) 자세한 정보에 대 한 합니다.  
  
## <a name="remarks"></a>설명  
 ML 및 ML64 명령줄 일부 옵션은 배치 구분 합니다. 예를 들어 여러는 ML 및 ML64 받아들일 수 있기 때문에 **/c** 옵션, 해당 **/Fo** 전에 옵션을 지정 해야 **/c**합니다. 다음 명령줄 예제에서는 각 어셈블리 파일 사양은 개체 파일 사양 수행 합니다.  
  
 **ml.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm**  
  
## <a name="environment-variables"></a>환경 변수  
  
|변수|설명|  
|--------------|-----------------|  
|INCLUDE|Include 파일 검색 경로를 지정합니다.|  
|ML|기본 명령줄 옵션을 지정합니다.|  
|TMP|임시 파일에 대 한 경로 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ML 오류 메시지](../../assembler/masm/ml-error-messages.md)   
 [Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)