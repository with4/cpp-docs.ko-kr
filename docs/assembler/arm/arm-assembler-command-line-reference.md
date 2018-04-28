---
title: ARM 어셈블러 명령줄 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f196b4aad76c72233c179249386dbb42960b31a6
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="arm-assembler-command-line-reference"></a>ARM 어셈블러 명령줄 참조
이 문서에서는 Microsoft ARM 어셈블러 명령줄 설명 *armasm*, Microsoft 구현에는 파일 형식 COFF (공용 개체) ARMv7 Thumb 어셈블리 언어를 컴파일합니다. 링커는 ARM 어셈블러 또는 라이브러리 관리자가 만든 개체 라이브러리와 함께 C 컴파일러에서 생성 되는 개체 코드를 사용 하 여 COFF 코드를 연결할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### <a name="parameters"></a>매개 변수  
 `options`  
 -오류 `filename`  
 오류 및 경고 메시지를 리디렉션 `filename`합니다.  
  
 -i `dir[;dir]`  
 포함 검색 경로에 지정 된 디렉터리를 추가 합니다.  
  
 -미리 정의 `directive`  
 기호를 미리 정의할 수 SETA, SETL, 또는 집합 지시문을 지정 합니다. 예: **armasm.exe-source.asm "SETA 150 COUNT"를 미리 정의할**합니다. 자세한 내용은 참조는 [ARM 어셈블러 도구 가이드](http://go.microsoft.com/fwlink/p/?linkid=246102)합니다.  
  
 -nowarn  
 모든 경고 메시지를 사용 하지 않도록 설정 합니다.  
  
 -무시 `warning`  
 지정 된 경고를 사용 하지 않도록 설정 합니다. 가능한 값에 대 한 경고에 대 한 섹션을 참조 합니다.  
  
 -도움말  
 명령줄 도움말 메시지를 인쇄 합니다.  
  
 -컴퓨터 `machine`  
 PE 헤더에서을 설정 하려면 컴퓨터 종류를 지정 합니다.  가능한 값에 대 한 `machine` 됩니다.  
**ARM**-컴퓨터 종류 IMAGE_FILE_MACHINE_ARMNT를 설정 합니다. 이 값이 기본값입니다.   
**THUMB**-컴퓨터 종류 IMAGE_FILE_MACHINE_THUMB를 설정 합니다.  
  
 -oldit  
 ARMv7 스타일 생성 IT 블록입니다.  기본적으로 ARMv8 호환 IT 블록이 생성 됩니다.  
  
 -를 통해 `filename`  
 추가 명령줄 인수 읽기 `filename`합니다.  
  
 -16  
 소스를 16 비트 Thumb 명령으로 어셈블하십시오.  이 값이 기본값입니다.  
  
 -32  
 소스를 32 비트 ARM 명령으로 어셈블하십시오.  
  
 -g  
 디버깅 정보를 생성 합니다.  
  
 -errorReport: `option`  
 지정 방법을 내부 어셈블러 오류를 Microsoft로 보고 됩니다.  가능한 값에 대 한 `option` 됩니다.   
**none**-보고서를 전송 하지 마십시오.   
**프롬프트**-사용자 보고서를 즉시 전송에 게 표시 합니다.   
**큐**-보고서를 보내려면 다음 관리자 로그온 사용자 메시지를 표시 합니다. 이 값이 기본값입니다.   
**보내기**-보고서를 자동으로 보냅니다.  
  
 `sourcefile`  
 소스 파일의 이름입니다.  
  
 `objectfile`  
 개체 (출력) 파일의 이름입니다.  
  
 다음 예제에서는 일반적인 시나리오의 armasm를 사용 하는 방법을 보여 줍니다. 먼저, armasm를 사용 하 여 개체 (.obj) 파일에는 어셈블리 언어 (.asm) 소스 파일을 빌드합니다. 그런 다음 (.c) 소스 파일을 컴파일하 CL 명령줄 C 컴파일러를 사용 하 고도 ARM 개체 파일에 연결 하려면 링커 옵션을 지정 합니다.  
  
 **armasm myasmcode.asm -o myasmcode.obj**  
  
 **cl myccode.c /link myasmcode.obj**  
  
## <a name="see-also"></a>참고 항목  
 [ARM 어셈블러 진단 메시지](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM 어셈블리 지시문](../../assembler/arm/arm-assembler-directives.md)