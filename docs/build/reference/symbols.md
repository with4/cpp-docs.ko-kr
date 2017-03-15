---
title: "/SYMBOLS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/symbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SYMBOLS dumpbin 옵션"
  - "공용 기호"
  - "기호 테이블"
  - "SYMBOLS dumpbin 옵션"
  - "-SYMBOLS dumpbin 옵션"
  - "기호, COFF 기호 테이블 표시"
  - "기호, 덤프하기"
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /SYMBOLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SYMBOLS  
```  
  
 이 옵션은 COFF 기호 테이블을 표시합니다.  기호 테이블은 모든 개체 파일에 있습니다.  이미지 파일이 \/DEBUG로 링크된 경우에만 COFF 기호 테이블은 이미지 파일에 나타납니다.  
  
 다음은 \/SYMBOLS 출력에 대한 설명입니다.  \/SYMBOLS 출력의 의미에 대한 추가 정보는 winnt.h\(IMAGE\_SYMBOL 및 IMAGE\_AUX\_SYMBOL\) 또는 COFF 설명서에서 찾을 수 있습니다.  
  
 다음 샘플 덤프를 참조하십시오.  
  
```  
Dump of file main.obj  
File Type: COFF OBJECT  
  
COFF    SYMBOL    TABLE  
000    00000000   DEBUG      notype      Filename      | .file  
      main.cpp  
002   000B1FDB   ABS      notype      Static      | @comp.id  
003   00000000   SECT1      notype      Static      | .drectve  
      Section length       26, #relocs   0, #linenums    0, checksum 722C964F  
005   00000000   SECT2      notype      Static      | .text  
      Section length      23, #relocs      1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)  
007   00000000   SECT2      notype ()   External      | _main  
008   00000000   UNDEF      notype ()   External      | ?MyDump@@YAXXZ (void __cdecl MyDump(void))  
  
String Table Size = 0x10 bytes  
  
Summary  
  
      26 .drectve  
      23 .text  
```  
  
## 설명  
 기호 번호로 시작하는 줄에 대한 다음 설명은 사용자와 관련된 정보가 있는 열을 설명합니다.  
  
-   첫 번째 세 자리 숫자는 기호 인덱스\/번호입니다.  
  
-   세 번째 열에 SECT*x*가 있는 경우 개체 파일의 해당 섹션에 기호가 정의됩니다.  반면 UNDEF가 나타난 경우 기호는 해당 개체에 정의되지 않으므로 다른 곳에서 확인되어야 합니다.  
  
-   다섯 번째 열\(Static, External\)은 기호가 해당 개체 내에서만 보이는지 또는 공용\(외부에서 보임\)인지 여부를 나타냅니다.  정적 기호 \_sym은 공용 기호 \_sym에 링크되지 않습니다. 이들은 이름이 \_sym인 함수의 서로 다른 두 인스턴스가 됩니다.  
  
 번호가 붙은 줄의 마지막 열은 기호의 데코레이팅된 이름 및 데코레이팅되지 않은 이름입니다.  
  
 [\/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은 [\/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)