---
title: "링커 도구 경고 LNK4237 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4237
dev_langs: C++
helpviewer_keywords: LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 718058dae02e9dfe9b653abea91993ec6662f5c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4237"></a>링커 도구 경고 LNK4237
지정한 'dll';에서 가져올 때 /subsystem: native가 : Console 또는 /SUBSYSTEM을 사용 합니다.  
  
 [/Subsystem: native가](../../build/reference/subsystem-specify-subsystem.md) (Win32) windows 응용 프로그램을 작성 하는 직접 사용 하는 경우 다음 중 하나 이상을 지정 되었습니다.  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   msvcrt * dll 중 하나입니다.  
  
 지정 하 여이 경고를 해결 **/subsystem: native가**합니다.