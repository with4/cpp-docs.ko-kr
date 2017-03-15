---
title: "ML and ML64 Command-Line Reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ML"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/W* MASM compiler option"
  - "/c MASM compiler option"
  - "/EP MASM compiler option"
  - "/Fe MASM compiler option"
  - "/Zp MASM compiler option"
  - "/AT MASM compiler option"
  - "/Zm MASM compiler option"
  - "/Sf MASM compiler option"
  - "/Sp MASM compiler option"
  - "/w MASM compiler option"
  - "/Fl MASM compiler option"
  - "/coff MASM compiler option"
  - "/St MASM compiler option"
  - "/Cx MASM compiler option"
  - "/Sl MASM compiler option"
  - "/Cu MASM compiler option"
  - "MASM (Microsoft Macro Assembler), ML command-line reference"
  - "/FPi MASM compiler option"
  - "/Zf MASM compiler option"
  - "ML environment variable"
  - "/Fr MASM compiler option"
  - "/help MASM compiler option"
  - "/Sa MASM compiler option"
  - "/Zd MASM compiler option"
  - "/I MASM compiler option"
  - "/? MASM compiler option"
  - "/Bl MASM compiler option"
  - "/Fm MASM compiler option"
  - "/Fo MASM compiler option"
  - "command-line reference [ML]"
  - "/Sn MASM compiler option"
  - "/Gd MASM compiler option"
  - "/D* MASM compiler option"
  - "environment variables, ML"
  - "/Gc MASM compiler option"
  - "/F* MASM compiler option"
  - "/Sc MASM compiler option"
  - "/H MASM compiler option"
  - "/Zs MASM compiler option"
  - "/omf MASM compiler option"
  - "/Sg MASM compiler option"
  - "/Cp MASM compiler option"
  - "/Zi MASM compiler option"
  - "/nologo MASM compiler option"
  - "/Sx MASM compiler option"
  - "/WX MASM compiler option"
  - "/Ss MASM compiler option"
  - "command line, reference [ML]"
  - "/Ta MASM compiler option"
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ML and ML64 Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

조합 하 고 하나 이상의 어셈블리 언어 소스 파일을 연결 합니다.  명령줄 옵션은 대 \/ 소문자 구분입니다.  
  
 Ml64.exe에 대 한 자세한 내용은 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## 구문  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### 매개 변수  
 `options`  
 다음 표에서 옵션입니다.  
  
|옵션|동작|  
|--------|--------|  
|**\/AT**|작은 메모리 모델을 지원할 수 있습니다.  .Com 형식 파일에 대 한 요구 사항을 위반 하는 코드 구문에 대 한 오류 메시지가 있습니다.  이렇게 하는 것과 아닙니다의  [.모델](../../assembler/masm/dot-model.md)**TINY** 지시문입니다.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Bl** `filename`|대체는 링커를 선택합니다.|  
|**\/c**|만 어셈블합니다.  연결 하지 않습니다.|  
|**\/coff**|개체 모듈의 공용 개체 파일 형식 \(COFF\) 형식을 생성합니다.  Win32 어셈블리 언어 개발에 일반적으로 필요 합니다.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Cp**|모든 사용자 식별자의 대\/소문자를 그대로 유지합니다.|  
|**\/Cu**|대문자 \(기본값\) 모든 식별자를 매핑합니다.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Cx**|공개 및 extern 심볼의 경우 유지 됩니다.|  
|**\/D** `symbol`\[\[\=`value`\]\]|지정 된 이름의 텍스트 매크로 정의합니다.  경우 `value` 입니다 누락, 비어 있습니다.  공백으로 구분 된 여러 토큰이 따옴표로 묶어야 합니다.|  
|**\/EP**|\(표준 출력 장치에 전송\) 소스 전처리 된 목록을 생성 합니다.  자세한 내용은 **\/Sf**를 참조하십시오.|  
|**\/ERRORREPORT** \[ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND** \]|Ml.exe 또는 ml64.exe 런타임 시에 실패 하는 경우 사용할 수 있습니다 **\/ERRORREPORT** 이러한 내부 오류에 대 한 정보를 Microsoft로 보낼 수 있습니다.<br /><br /> **\/ERRORREPORT**에 대한 자세한 내용은 [\/errorReport\(내부 컴파일러 오류 보고\)](../../build/reference/errorreport-report-internal-compiler-errors.md)를 참조하십시오.|  
|**\/F** `hexnum`|스택 크기를 설정 `hexnum` 바이트 \(동일입니다 **\/link\/STACK**:`number`\).  값 16 진수 표기법으로 표현 해야 합니다.  사이 공백이 있어야 **\/F** 및 `hexnum`.|  
|**\/Fe** `filename`|실행 파일의 이름을 지정 합니다.|  
|**\/Fl**\[\[`filename`\]\]|어셈블된 코드를 생성합니다.  자세한 내용은 **\/Sf**를 참조하십시오.|  
|**\/Fm**\[\[`filename`\]\]|링커에서 맵 파일을 만듭니다.|  
|**\/Fo** `filename`|개체 파일의 이름을 지정 합니다.  자세한 내용은 설명 단원을 참조 하십시오.|  
|**\/FPi**|에뮬레이터 수정은 부동 소수점 연산 \(혼합된 언어에만 해당\)를 생성합니다.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Fr**\[\[`filename`\]\]|소스 브라우저.sbr 파일을 생성합니다.|  
|**\/FR**\[\[`filename`\]\]|소스 브라우저.sbr 파일의 확장된 된 형태를 생성합니다.|  
|**\/Gc**|포트란 또는 파스칼 스타일의 함수를 호출 하 고 명명 규칙을 지정 합니다.  Same as **OPTION LANGUAGE:PASCAL**.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Gd**|C 스타일 함수를 호출 하 고 명명 규칙을 지정 합니다.  Same as **OPTION LANGUAGE:C**.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/GZ**|\_\_Stdcall 함수 호출 및 명명 규칙의 사용을 지정 합니다.  Same as **OPTION LANGUAGE:STCALL**.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/H** `number`|외부 이름의 많은 문자 수를 제한합니다.  기본값은 31 자입니다.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/help**|ML에 대 한 도움말 Quickhelp를 호출합니다.|  
|**\/I** `pathname`|설정 경로 포함 파일입니다.  최대 10 개의 **\/I** 옵션을 사용할 수 있습니다.|  
|**\/nologo**|실패 한 어셈블리에 대 한 메시지를 표시 하지 않습니다.|  
|**\/omf**|개체 모듈의 모듈 파일 OMF \(형식\) 형식의 개체를 생성합니다.  **\/omf**implies **\/c**; Ml.exe는 OMF 개체 연결을 지원 하지 않습니다.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Sa**|모든 사용 가능한 정보의 목록을 설정합니다.|  
|**\/safeseh**|예외 처리기가 포함 된 또는 모든 선언 된 예외 처리기를 포함 하는 개체를 표시 합니다.  [.SAFESEH](../../assembler/masm/dot-safeseh.md).<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Sf**|첫번째 목록 목록에 파일을 추가합니다.|  
|**\/Sl** `width`|줄 당 문자 수를 나열 하는 소스 줄 너비를 설정 합니다.  범위는 60 ~ 255 또는 0입니다.  기본값은 0입니다.  다른 이름으로 동일한  [페이지](../../assembler/masm/page.md) 너비입니다.|  
|**\/Sn**|목록을 만들 때 기호 테이블을 끕니다.|  
|**\/Sp** `length`|페이지 당 줄에 나열 된 원본 페이지 길이 설정 합니다.  범위는 0 또는 10에서 255 사이입니다.  기본값은 0입니다.  다른 이름으로 동일한  [페이지](../../assembler/masm/page.md) 길이입니다.|  
|**\/Ss** `text`|소스 목록에 대 한 텍스트를 지정합니다.  다른 이름으로 동일한  [자막](../../assembler/masm/subtitle.md) 텍스트입니다.|  
|**\/St** `text`|소스 목록에 대 한 제목을 지정합니다.  다른 이름으로 동일한  [제목](../../assembler/masm/title.md) 텍스트입니다.|  
|**\/Sx**|False 이면 조건 목록에서에 설정합니다.|  
|**\/Ta** `filename`|어셈블 원본 파일 이름을.asm 확장명으로 끝나지 않습니다.|  
|**\/w**|Same as **\/W0\/WX**.|  
|**\/W** `level`|경고 수준을 설정 하는 `level` \= 0, 1, 2 또는 3입니다.|  
|**\/WX**|경고가 발생 하는 경우 오류 코드를 반환 합니다.|  
|**\/X**|INCLUDE 환경 경로 무시 합니다.|  
|**\/Zd**|개체 파일의 줄 번호 정보를 생성합니다.|  
|**\/Zf**|모든 기호는 공개 됩니다.|  
|**\/Zi**|CodeView 정보가 개체 파일을 생성합니다.|  
|**\/Zm**|수 있도록**M510** 호환성을 MASM 5.1에 대 한 옵션입니다.<br /><br /> Ml64.exe에서는 사용할 수 없습니다.|  
|**\/Zp**\[\[`alignment`\]\]|지정 된 바이트 경계에서 구조체를 압축 합니다.  `alignment` 1, 2 또는 4 될 수 있습니다.|  
|**\/Zs**|구문 확인만 수행합니다.|  
|**\/?**|ML 명령줄 구문 요약을 표시 합니다.|  
  
 `filename`  
 파일 이름입니다.  
  
 `linkoptions`  
 링크 옵션입니다.  자세한 내용은 [링커 옵션](../../build/reference/linker-options.md)를 참조하십시오.  
  
## 설명  
 일부 명령줄 옵션 ML 및 ML64 배치에 민감한입니다.  예를 들어, ML 및 ML64 몇 가지 받아들일 수 있기 때문에 **\/c** 옵션 모든 해당 **\/Fo** 하기 전에 옵션을 지정 해야 **\/c**.  다음 명령줄 예제는 각 어셈블리 파일 사양에 대 한 개체 파일 사양을 보여 줍니다.  
  
 **ml.exe \/Fo a1.obj \/c a.asm \/Fo b1.obj \/c b.asm**  
  
## 환경 변수  
  
|변수|설명|  
|--------|--------|  
|포함|포함 파일 검색 경로를 지정합니다.|  
|ML|기본 명령줄 옵션을 지정합니다.|  
|TMP|임시 파일 경로를 지정합니다.|  
  
## 참고 항목  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)   
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)