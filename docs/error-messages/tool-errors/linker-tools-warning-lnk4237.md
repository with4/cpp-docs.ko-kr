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
ms.openlocfilehash: fcc109fe3ccf06e0461deed449517850271a2024
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39209393"
---
# <a name="linker-tools-warning-lnk4237"></a>링커 도구 경고 LNK4237
'Dll';에서 가져올 때 지정한 /SUBSYSTEM:NATIVE /Subsystem: console 또는 /subsystem: windows를 사용 합니다.  
  
 [/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) Win32 windows 응용 프로그램을 빌드하는 직접 사용 하는 경우 다음 중 하나 이상 지정 되었습니다.  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   하나는 msvcrt\* dll입니다.  
  
 지정 하지 않는 하 여이 경고를 해결할 **/SUBSYSTEM:NATIVE**합니다.