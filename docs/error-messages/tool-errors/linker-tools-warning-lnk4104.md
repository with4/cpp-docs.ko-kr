---
title: 링커 도구 경고 LNK4104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9ea3e074cc0db9591cd0ffe9329ff7f1936563f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4104"></a>링커 도구 경고 LNK4104
'symbol' 기호의 내보내기는 PRIVATE 이어야 합니다.  
  
 `symbol` 다음 중 하나일 수 있습니다.  
  
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
  
 이 경고는 DLL에 대 한 가져오기 라이브러리를 빌드하는 경우에 내보내집니다 및 모듈 정의 파일에서 PRIVATE으로 지정 하지 않고 위의 함수 중 하나를 내보내기. 일반적으로 이러한 함수는 OLE에 의해 사용 하기 위해 내보내집니다. 가져오기 라이브러리에 링크 된 프로그램이 라이브러리에 올바르게가 함수 호출을 만들 때 특별 한 동작이 발생할 수 있습니다. PRIVATE 키워드에 대 한 자세한 내용은 참조 [내보내기](../../build/reference/exports.md)합니다.