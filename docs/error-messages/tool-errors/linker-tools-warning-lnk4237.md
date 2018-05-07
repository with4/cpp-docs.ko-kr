---
title: 링커 도구 경고 LNK4237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4237
dev_langs:
- C++
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5acccf52d3738985c7a83432342952af03bf78b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4237"></a>링커 도구 경고 LNK4237
지정한 'dll';에서 가져올 때 /subsystem: native가 : Console 또는 /SUBSYSTEM을 사용 합니다.  
  
 [/Subsystem: native가](../../build/reference/subsystem-specify-subsystem.md) (Win32) windows 응용 프로그램을 작성 하는 직접 사용 하는 경우 다음 중 하나 이상을 지정 되었습니다.  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   msvcrt * dll 중 하나입니다.  
  
 지정 하 여이 경고를 해결 **/subsystem: native가**합니다.