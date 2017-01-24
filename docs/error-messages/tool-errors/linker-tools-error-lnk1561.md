---
title: "링커 도구 오류 LNK1561 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1561"
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

진입점이 정의되어야 합니다.  
  
 링커가 진입점을 찾지 못했습니다.  DLL로 링크하려고 했을 수 있습니다. 이 경우, [\/DLL](../../build/reference/dll-build-a-dll.md) 옵션을 사용하여 링크해야 합니다.  진입점의 이름을 지정하는 것을 잊었을 수도 있습니다. 이 경우, [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) 옵션을 사용하여 링크합니다.  
  
 그렇지 않은 경우, 코드에 main, wmain, WinMain 또는 wMain 함수를 포함해야 합니다.  
  
 [LIB](../../build/reference/lib-reference.md)를 사용하여 .dll을 빌드하려는 경우 이 오류가 발생하는 원인 중 한 가지는 .def 파일을 제공했기 때문입니다.  이 경우에는 .def 파일을 빌드에서 제거하십시오.  
  
 다음 샘플에서는 LNK1561 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```