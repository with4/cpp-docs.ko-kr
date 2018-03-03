---
title: "링커 도구 오류 LNK1245 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 142d88489748f30308395d64f3db78178a9b856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1245"></a>링커 도구 오류 LNK1245
잘못 된 하위 시스템 '하위 시스템'; /SUBSYSTEM은 WINDOWS, WINDOWSCE 또는 CONSOLE 이어야 합니다.  
  
 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 개체를 컴파일하는 데 사용한 다음 조건 중 하나가 되었으며:  
  
-   사용자 지정 진입점이 정의 되었습니다 ([/ENTRY](../../build/reference/entry-entry-point-symbol.md))을 링커에 하위 시스템을 유추할 수 없습니다.  
  
-   에 전달 된 값은 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) /clr 개체에 대 한 유효 하지 않은 링커 옵션입니다.  
  
 두 경우 모두에 대 한 해상도 /SUBSYSTEM 링커 옵션에 유효한 값을 지정 하는 것입니다.