---
title: "의사 대상 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 761b71f05840c86516563df79d45cc1bb018fbba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pseudotargets"></a>의사 대상
의사 대상은 종속 줄에서 파일 이름 대신 사용 되는 레이블입니다. 존재 하지 않는 이므로 오래 된 파일으로 해석 됩니다. NMAKE는 의사 타임 스탬프는 모든 종속 파일 중 가장 최근 가정 합니다. 종속이 없는 경우 현재 시간으로 가정 됩니다. 의사 대상을 대상으로 사용할 경우 해당 명령은 항상 실행 됩니다. 종속으로 사용 하는 의사 해야 다른 종속성의 대상으로도 표시 됩니다. 그러나 해당 종속성 명령 블록을 소유 하지 않아도 됩니다.  
  
 의사 대상 이름은 대상에 대 한 파일 이름 구문 규칙을 따릅니다. 그러나 이름에 확장명이 없는 경우 (즉, 포함 되지 않은 기간), 파일 이름에 대 한 8 자 제한을 초과 하 고 최대 256 자까지 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [대상](../build/targets.md)