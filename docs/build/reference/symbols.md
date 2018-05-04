---
title: -SYMBOLS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /symbols
dev_langs:
- C++
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a0cc59ee730fcfad47d758dec73cb8646210934
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="symbols"></a>/SYMBOLS
```  
/SYMBOLS  
```  
  
 이 옵션은 COFF 기호 테이블을 표시합니다. 기호 테이블은 모든 개체 파일에 존재 합니다. COFF 기호 테이블 /DEBUG으로 연결 된 경우에 이미지 파일에 나타납니다.  
  
 다음은 실행에 대 한 출력에 대 한 설명을 합니다. /SYMBOLS 출력의 의미에 대 한 추가 정보 (IMAGE_SYMBOL 및 IMAGE_AUX_SYMBOL) winnt.h 또는 COFF 설명서에서 찾을 수 있습니다.  
  
 다음 샘플 덤프를 가정합니다.  
  
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
  
## <a name="remarks"></a>설명  
 다음 설명을 기호, 숫자로 시작 하는 줄에 대 한 사용자와 관련 된 정보가 있는 열을 설명 합니다.  
  
-   첫 번째 3 자리 수 기호 인덱스/수가입니다.  
  
-   세 번째 열 섹션에 있는 경우*x*, 기호가 개체 파일의 해당 섹션에 정의 합니다. 하지만 UNDEF 표시 되 면 해당 개체에 정의 되지 않았습니다 고 다른 곳에서 확인 해야 합니다.  
  
-   다섯 번째 열 (정적, 외부) 기호를 해당 개체 내 에서만 표시 되는지 여부 또는 공용 인지 알려 줍니다 (표시 외부에서). 정적 기호 _sym 공용 기호 _sym;에 연결할 수 없습니다. 이 이름이 _sym 함수의 서로 다른 두 인스턴스가 됩니다.  
  
 번호가 매겨진된 줄의 마지막 열 기호 이름이 고, 둘 다 데코레이팅된 및 데코 레이트 되지 않은 합니다.  
  
 만 [/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은으로 생성 된 파일에서 사용 하기 위해 사용할 수는 [/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)