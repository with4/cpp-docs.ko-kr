---
title: "ARM Assembler Diagnostic Messages | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Diagnostic Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft ARM 어셈블러 \(*armasm*\)을 발견 하면 진단 경고 및 오류를 생성 합니다.  가장 일반적으로 발생 하는 메시지에 설명 합니다.  
  
## 구문  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## 진단 메시지  
  
### 오류  
 A2193:이 명령의 예기치 않은 동작이 생성 됩니다.  
 ARM 아키텍처는이 명령이 실행 될 때 일어나는 보장할 수 없습니다.  잘 정의 된 폼이 명령에 대 한 자세한 내용은 참조는 [ARM 아키텍처 참조 설명서](http://go.microsoft.com/fwlink/?LinkId=246464).  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196: 명령에서 16 비트 인코딩할 수 없습니다  
 지정한 명령 16 비트 엄지 명령으로 인코딩할 수 없습니다.  지정 된 32 비트 명령 또는 16 비트 명령 범위에 레이블을 표시 하는 코드를 다시 정렬 합니다.  
  
 분기 32\-비트 인코딩할 수 있더라도 어셈블러 16 비트에서 분기를 인코딩하고이 오류와 함께 실패할 시도할 수 있습니다.  사용 하 여이 문제를 해결할 수 있는 `.W` 분기 32 비트로 명시적으로 표시 하려면 지정자.  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 A2202: 전 UAL 명령 구문 엄지 영역에서 사용할 수 없습니다.  
 Thumb 코드 통합 어셈블러 언어 \(UAL\) 구문을 사용 해야 합니다.  이전 구문은 더 이상 허용 됩니다.  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513: 회전도 여야 합니다.  
 ARM 모드로 가지 상수를 지정 하는 대체 구문이입니다.  대신 `#<const>`를 쓸 수 있습니다 `#<byte>,#<rot>`, 상수 값을 회전 하 여 얻은 값을 나타내는 `<byte>` 오른쪽으로 `<rot>`.  이 구문을 사용 하면 값을 확인 해야 `<rot>` 도 합니다.  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557: 잘못 된 바이트 수를 다시 쓰기  
 네온 구조에 로드 하 고 저장 명령 \(`VLDn`, `VSTn`\), 쓰기 되돌림 기본 레지스터를 지정 하는 대체 구문입니다.  주소 뒤에 느낌표 \(\!\)를 넣는 대신 즉시 기본 레지스터에 추가할 오프셋을 나타내는 값을 지정할 수 있습니다.  이 구문을 사용 하는 경우 정확한 바이트 수를 명령으로 저장 되거나 로드를 지정 해야 합니다.  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### 경고  
 A4228: 영역 맞춤을 맞춤 값을 초과 했습니다. 맞춤 보장  
 지정 된 맞춤은 `ALIGN` 지시문이 바깥쪽 맞춤 보다 큰 `AREA`.  어셈블러는 보장할 수 없습니다 결과적으로 `ALIGN` 지시문을 유지할 수 있습니다.  
  
 이 문제를 해결 하려면 사용자 지정할 수 있습니다에서 `AREA` 지시문은 `ALIGN` 원하는 맞춤 보다 크거나 특성.  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508:이 회전 된 상수의 사용 되지  
 ARM 모드로 가지 상수를 지정 하는 대체 구문이입니다.  대신 `#<const>`를 쓸 수 있습니다 `#<byte>,#<rot>`, 상수 값을 회전 하 여 얻은 값을 나타내는 `<byte>` 오른쪽으로 `<rot>`.  일부 상황에서 ARM 회전된 이러한 상수를 사용 하는 더 이상 사용 했습니다.  이러한 경우에는 basic 사용 `#<const>` 구문 대신 합니다.  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509:이 명령의 형태를 조건부 사용 되지 않습니다.  
 이 명령의 형태를 조건부 ARM ARMv8 아키텍처에 의해 거부 되었습니다.  조건부 분기를 사용 하 여 코드를 변경 하는 것이 좋습니다.  어떤 조건부 지침 여전히 지 보려면 참조는 [ARM 아키텍처 참조 안내서](http://go.microsoft.com/fwlink/?LinkId=246464).  
  
 이 경고를 하지 않습니다 때 방출은  `-oldit` 명령줄 스위치가 사용.  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## 참고 항목  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)