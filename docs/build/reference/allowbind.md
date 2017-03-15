---
title: "/ALLOWBIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALLOWBIND editbin 옵션"
  - "/ALLOWBIND editbin 옵션"
  - "-ALLOWBIND editbin 옵션"
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ALLOWBIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DLL을 다시 실행할 것인지를 지정합니다.  
  
```  
  
/ALLOWBIND[:NO]  
  
```  
  
## 설명  
 **\/ALLOWBIND**는 DLL의 헤더에 1비트를 설정하여 Bind.exe에서 이미지를 바인딩할 수 없도록 합니다.  바인딩 이미지 로더 기준 다시 지정 하 고 참조 되는 각 DLL에 대 한 주소 픽스업을 수행할 수 없을 때 더 빠르게 로드할 수 있습니다.  디지털 서명이 있는 DLL의 경우에는 —바인딩하면 서명이 무효화되므로 바인딩하지 않을 수 있습니다.  바인딩에 영향을 주지 않습니다 주소 공간 레이아웃 불규칙화 \(ASLR\)를 사용 하 여 이미지에 대해 활성화 된 경우  **\/DYNAMICBASE**  ASLR 지 원하는 Windows 버전에서 가능합니다.  
  
 **\/ALLOWBIND:NO**  Bind.exe에서 DLL 바인딩 방지 하기 위해 사용합니다.  
  
 자세한 내용은 [\/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) 링커 옵션을 참조하십시오.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)