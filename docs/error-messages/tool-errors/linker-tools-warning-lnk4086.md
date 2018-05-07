---
title: 링커 도구 경고 LNK4086 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7b3ad3a8ceebf97ccdcf7a1d8079886f54a3984
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4086"></a>링커 도구 경고 LNK4086
entrypoint 'function' 'number' 바이트; 인수가 있는 __stdcall이 아닙니다. 이미지가 실행 되지 않습니다.  
  
 Dll의 진입점 이어야 `__stdcall`합니다. 사용 하 여 함수를 다시 컴파일해야 하나는 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) 다시 실행 하거나 지정 `__stdcall` 또는 함수를 정의할 때 WINAPI 합니다.