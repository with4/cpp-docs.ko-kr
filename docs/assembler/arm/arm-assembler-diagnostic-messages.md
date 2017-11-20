---
title: "ARM 어셈블러 진단 메시지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6457e82928a5a705377b90e2acc0989768fcd9f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM 어셈블러 진단 메시지
Microsoft ARM 어셈블러 (*armasm*)가 발견 될 때 진단 경고와 오류를 내보냅니다. 이 문서에서는 가장 일반적으로 발생 한 메시지를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## <a name="diagnostic-messages"></a>진단 메시지  
  
### <a name="errors"></a>오류  
 이 명령은 A2193: 예기치 않은 동작이 생성  
 ARM 아키텍처는이 명령이 실행 될 때 수행 되는 작업을 보장할 수 없습니다.  이 명령의 잘 정의 된 형식에 대 한 세부 정보를 참조 하십시오.는 [ARM 아키텍처 참조 설명서](http://go.microsoft.com/fwlink/?LinkId=246464)합니다.  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196: 16 비트에서 명령 인코딩할 수 없습니다  
 지정 된 명령 16 비트 Thumb 명령으로 인코딩할 수 없습니다.  지정 된 32 비트 명령 또는 범위의 16 비트 명령으로 대상 레이블에 가져올 코드를 다시 정렬 합니다.  
  
 어셈블러는 인코딩할 수는 32 비트 분기를 16 비트에서 분기를 인코딩하고이 오류로 인해 실패 시도할 수 있습니다. 사용 하 여이 문제를 해결할 수는 `.W` 지정자를 32 비트로 분기를 명시적으로 표시 합니다.  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 엄지 단추 영역에 사용할 수 없습니다: A2202 이전 UAL 명령 구문  
 Thumb 코드가 어셈블러 언어 통합 (UAL) 구문을 사용 해야 합니다.  이전 구문은 더 이상 허용  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513: 회전 짝수 여야 합니다.  
 ARM 모드에서 상수를 지정 하기 위한 대체 구문이 있습니다.  작성 하는 대신 `#<const>`를 작성할 수 있습니다 `#<byte>,#<rot>`, 값을 회전 하 여 얻은 상수 값을 나타내는 `<byte>` 오른쪽으로 `<rot>`합니다.  값을 확인 해야이 구문을 사용 하는 경우 `<rot>` 도 합니다.  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557: 잘못 된 다시 쓸 바이트 수  
 NEON 구조에 로드 및 저장 지침 (`VLDn`, `VSTn`), 쓰기 저장을 기본 레지스터를 지정 하기 위한 구문은 대체 합니다.  주소는 다음에 느낌표 (!)를 배치 하는 대신 기본 레지스터에 추가할 수에 대 한 오프셋을 표시 하는 즉시 값을 지정할 수 있습니다.  이 구문을 사용 하는 경우 정확한 로드 되거나 해당 명령에 의해 저장 된 바이트 수를 지정 해야 합니다.  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### <a name="warnings"></a>경고  
 A4228: 맞춤 값이 초과 영역 맞춤; 맞춤 보장 되지 않습니다  
 에 지정 된 맞춤은 `ALIGN` 지시문 묶는 맞춤 보다 크면 `AREA`합니다.  결과적으로, 어셈블러는 보장할 수 없습니다는 `ALIGN` 지시문이 적용 됩니다.  
  
 이 해결 하려면에 지정할 수 있습니다는 `AREA` 지시문은 `ALIGN` 원하는 맞춤 보다 크거나 같은 특성이 있습니다.  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508:이 회전 된 상수를 사용 하는 사용 되지 않습니다.  
 ARM 모드에서 상수를 지정 하기 위한 대체 구문이 있습니다.  작성 하는 대신 `#<const>`를 작성할 수 있습니다 `#<byte>,#<rot>`, 값을 회전 하 여 얻은 상수 값을 나타내는 `<byte>` 오른쪽으로 `<rot>`합니다.  일부 컨텍스트에서 ARM는 이상 사용 되지 이러한 회전 된 상수를 사용 하 합니다. 이러한 경우에는 기본 사용 `#<const>` 구문 대신 합니다.  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509: 조건부 명령의이 형태는 사용 되지 않습니다.  
 이러한 형태의 조건부 명령 되지 ARMv8 아키텍처의 ARM입니다. 조건부 분기를 사용 하도록 코드를 변경 하는 것이 좋습니다. 어떤 조건부 명령을 계속 지원를 보려면 참조는 [ARM 아키텍처 참조 설명서](http://go.microsoft.com/fwlink/?LinkId=246464)합니다.  
  
 이 경고가 때 내보낸는 `-oldit` 명령줄 스위치를 사용 합니다.  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [ARM 어셈블러 명령줄 참조](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM 어셈블리 지시문](../../assembler/arm/arm-assembler-directives.md)