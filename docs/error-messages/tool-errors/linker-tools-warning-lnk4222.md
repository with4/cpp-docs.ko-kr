---
title: 링커 도구 경고 LNK4222 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 359af4c4d3b1079b2d56f108bff0ee1488ea71f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4222"></a>링커 도구 경고 LNK4222
내보낸된 'symbol' 기호는 서 수로 지정 해야  
  
 서 수로 다음과 같은 기호를 내보내지 않아야 합니다.  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 이름으로 항상 있는 이러한 함수를 사용 하 여 `GetProcAddress`합니다. 이 대해 링커 경고 내보내기 유형은 더 큰 이미지를 생성할 수 있으므로 합니다. 서 수 내보내기의 범위는 비교적 적은 내보내기로 큰 경우 발생할 수 있습니다. 예를 들어 개체에 적용된  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 (2-99) 위의 그중에서 98 내보내기 주소 테이블에 100 슬롯이 필요 합니다. 다른 한편으로는  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 두 슬롯을 필요 합니다. (으로 내보낼 수 있음을 유의 [/내보내기](../../build/reference/export-exports-a-function.md) 링커 옵션.)