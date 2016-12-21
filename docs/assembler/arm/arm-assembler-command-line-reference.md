---
title: "ARM Assembler Command-Line Reference | Microsoft Docs"
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
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 Microsoft ARM 어셈블러, 명령줄에서는  *armasm*, ARMv7 엄지 어셈블리 언어 Microsoft 구현에는 COFF \(공용 개체 파일 형식\)로 컴파일합니다.  링커는 COFF 코드로 ARM 어셈블러 또는 C 컴파일러, 라이브러리 관리자에 의해 작성 된 개체 라이브러리를 함께 사용 하 여 생성 된 개체 코드를 연결할 수 있습니다.  
  
## 구문  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### 매개 변수  
 `options`  
 \-오류`filename`  
 오류 및 경고 메시지를 리디렉션하고 `filename`.  
  
 \-i`dir[;dir]`  
 지정 된 디렉터리 포함 검색 경로에 추가 합니다.  
  
 \-미리 정의`directive`  
 SETA, SETL, 또는 세트 지시문 기호를 미리 정의할 수를 지정 합니다.  예를 들어, **armasm.exe \-predefine "COUNT SETA 150" source.asm** 같은 형식입니다.  자세한 내용은 [ARM 어셈블러 도구 가이드](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 \-nowarn  
 모든 경고 메시지를 해제 합니다.  
  
 \-무시`warning`  
 지정 된 경고를 비활성화 합니다.  가능한 값에 대 한 경고에 대 한 섹션을 참고 하십시오.  
  
 \-도움말  
 명령줄 도움말 메시지를 인쇄 합니다.  
  
 \-컴퓨터`machine`  
 PE 헤더에 설정 하는 컴퓨터 종류를 지정 합니다.  가능한 값에 대 한 `machine` 입니다.   
**ARM**\-IMAGE\_FILE\_MACHINE\_ARMNT에에서 컴퓨터 종류를 설정합니다.  이 값이 기본값입니다.   
**THUMB**\-IMAGE\_FILE\_MACHINE\_THUMB에에서 컴퓨터 종류를 설정합니다.  
  
 \-oldit  
 ARMv7 스타일 생성 IT 블록.  기본적으로 ARMv8 호환 IT 블록이 생성 됩니다.  
  
 \-통해`filename`  
 추가 명령줄 인수를 읽을 `filename`.  
  
 \-16  
 16 비트 엄지 지침으로 소스를 어셈블하십시오.  이 값이 기본값입니다.  
  
 \-32  
 32 비트 ARM 명령어와 소스를 어셈블하십시오.  
  
 \-g  
 디버깅 정보를 생성 합니다.  
  
 \-errorReport:`option`  
 어떻게 내부 어셈블러 Microsoft로 오류 보고를 지정 합니다.  가능한 값에 대 한 `option` 입니다.   
**none**\-보고서를 보내지 마십시오.   
**prompt**\-즉시 보고서를 보낼 것인지 묻습니다.   
**queue**\-다음 admin 로그온 할 때 보고서를 보낼 것인지 묻습니다.  이 값이 기본값입니다.   
**send**\-보고서를 자동으로 보냅니다.  
  
 `sourcefile`  
 소스 파일의 이름입니다.  
  
 `objectfile`  
 \(출력\) 개체 파일의 이름입니다.  
  
 다음 예제에서는 일반적인 시나리오에서는 armasm를 사용 하는 방법을 보여 줍니다.  먼저 armasm를 사용 하 여 개체 파일 \(.obj\)에 어셈블리 언어 소스 \(.asm\) 파일을 작성 합니다.  CL 명령줄 C 컴파일러를 사용 하 여 \(.c\) 소스 파일을 컴파일하는 데 고 ARM 개체 파일을 연결 하기 위한 링커 옵션을 지정할 수도 있습니다.  
  
 **armasm myasmcode.asm \-o myasmcode.obj**  
  
 **cl myccode.c \/link myasmcode.obj**  
  
## 참고 항목  
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)