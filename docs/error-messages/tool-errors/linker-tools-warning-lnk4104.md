---
title: "링커 도구 경고 LNK4104 | Microsoft Docs"
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
  - "LNK4104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4104"
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' 기호의 내보내기는 PRIVATE여야 합니다.  
  
 `symbol`이 다음 중 하나일 수 있습니다.  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 이 경고는 모듈 정의 파일에서 DLL에 대한 가져오기 라이브러리 및 위의 함수에 대한 내보내기 라이브러리를 PRIVATE으로 지정하지 않은 채로 빌드하는 경우에 발생합니다.  일반적으로 이러한 함수는 OLE에 의해 내보내져서 사용됩니다.  라이브러리에 링크된 프로그램이 잘못된 함수 호출을 발생시키는 경우에 함수를 가져오기 라이브러리에 배치하면 특별한 동작이 발생합니다.  PRIVATE 키워드에 대한 자세한 내용은 [EXPORTS](../../build/reference/exports.md)를 참조하십시오.