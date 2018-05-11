---
title: 링커 도구 오류 LNK1245 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47a1c2e5f7bf66946dcc5816d7a20fd485b59b45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1245"></a>링커 도구 오류 LNK1245
잘못 된 하위 시스템 '하위 시스템'; /SUBSYSTEM은 WINDOWS, WINDOWSCE 또는 CONSOLE 이어야 합니다.  
  
 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 개체를 컴파일하는 데 사용한 다음 조건 중 하나가 되었으며:  
  
-   사용자 지정 진입점이 정의 되었습니다 ([/ENTRY](../../build/reference/entry-entry-point-symbol.md))을 링커에 하위 시스템을 유추할 수 없습니다.  
  
-   에 전달 된 값은 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) /clr 개체에 대 한 유효 하지 않은 링커 옵션입니다.  
  
 두 경우 모두에 대 한 해상도 /SUBSYSTEM 링커 옵션에 유효한 값을 지정 하는 것입니다.