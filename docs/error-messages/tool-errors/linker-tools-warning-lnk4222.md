---
title: "링커 도구 경고 LNK4222 | Microsoft Docs"
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
  - "LNK4222"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4222"
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4222
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

내보낸 'symbol' 기호를 서수로 지정하면 안 됩니다.  
  
 다음 기호를 서수로 내보내면 안 됩니다.  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 이러한 함수는 항상 `GetProcAddress`를 사용하여 이름을 기준으로 찾습니다.  이 종류의 내보내기는 대형 이미지를 생성할 수 있으므로 링커는 이러한 내보내기를 경고합니다.  이 경고는 내보내기의 수가 비교적 적으며 동시에 서수 내보내기의 범위가 큰 경우에 발생할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 위의 코드에서 98개\(2\-99\)의 필터로 구성된 내보내기 주소 테이블에는 슬롯이 100개 필요한  반면에,  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 위의 코드에는 슬롯이 두 개 필요합니다. [\/EXPORT](../../build/reference/export-exports-a-function.md) 링커 옵션으로 내보낼 수 있음을 기억하십시오.