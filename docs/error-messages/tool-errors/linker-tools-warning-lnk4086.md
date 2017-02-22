---
title: "링커 도구 경고 LNK4086 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4086"
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 링커 도구 경고 LNK4086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' 진입점이 12바이트 인수가 있는 \_\_stdcall이 아닙니다. 이미지가 실행되지 않을 수도 있습니다.  
  
 DLL의 진입점은 `__stdcall`이어야 합니다.  [\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) 옵션으로 함수를 다시 컴파일하거나 함수를 정의할 때 `__stdcall` 또는 WINAPI를 지정하십시오.