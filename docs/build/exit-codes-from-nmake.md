---
title: "NMAKE의 종료 코드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13cbe4806d8b3960cbf80df41c7cce6e7657ba7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exit-codes-from-nmake"></a>NMAKE의 종료 코드
NMAKE 다음 종료 코드를 반환합니다.  
  
|코드|의미|  
|----------|-------------|  
|0|오류 없음 (경고 가능)|  
|1|불완전 한 빌드 (/K을 사용한 경우에 발생)|  
|2|다음 중 하나 때문일 프로그램 오류:|  
||-메이크파일의의 구문 오류|  
||-명령에서는 오류 또는 종료 코드|  
||-사용자가 중단|  
|4|시스템 오류-메모리가 부족|  
|255|대상이 최신 상태가 아닙니다 (/Q를 사용한 경우에 실행)|  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 실행](../build/running-nmake.md)