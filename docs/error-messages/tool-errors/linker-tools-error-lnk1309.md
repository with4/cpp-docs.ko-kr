---
title: "링커 도구 오류 LNK1309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1309"
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 오류 LNK1309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type1 모듈이 발견되었습니다. \/CLRIMAGETYPE:type2 스위치를 사용할 수 없습니다.  
  
 **\/CLRIMAGETYPE**을 사용하여 CLR 이미지를 요청했지만 하나 이상의 모듈이 이 형식과 호환되지 않으므로 링커가 이 형식의 이미지를 생성할 수 없습니다.  
  
 예를 들어, **\/CLRIMAGETYPE:safe**를 지정하고 **\/clr:pure**를 사용하여 빌드된 모듈을 전달하면 LNK1309 오류가 발생합니다.  
  
 ptrustu\[d\].lib를 사용하여 부분 신뢰 CLR 순수 응용 프로그램을 빌드하려고 하는 경우에도 LNK1309가 발생할 수 있습니다.  부분 신뢰 응용 프로그램을 만드는 방법에 대한 자세한 내용은 [방법: CRT 라이브러리 DLL에 대한 종속성을 제거하여 부분적으로 신뢰할 수 있는 응용 프로그램 만들기](../../dotnet/create-a-partially-trusted-application.md)를 참조하십시오.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [\/CLRIMAGETYPE\(CLR 이미지 형식 지정\)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)를 참조하십시오.