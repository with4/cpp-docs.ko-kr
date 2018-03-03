---
title: "링커 도구 경고 LNK4086 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcd701401c798d7126be4f4239ee533b14d90652
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4086"></a>링커 도구 경고 LNK4086
entrypoint 'function' 'number' 바이트; 인수가 있는 __stdcall이 아닙니다. 이미지가 실행 되지 않습니다.  
  
 Dll의 진입점 이어야 `__stdcall`합니다. 사용 하 여 함수를 다시 컴파일해야 하나는 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) 다시 실행 하거나 지정 `__stdcall` 또는 함수를 정의할 때 WINAPI 합니다.