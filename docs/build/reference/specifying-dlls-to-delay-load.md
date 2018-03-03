---
title: "지연 로드할 Dll 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7c04b0885228bcef65b1b53cda6d28dc6755379
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-dlls-to-delay-load"></a>지연 로드할 DLL 지정
지연 Dll 로드 된 방식으로 로드를 지정할 수는 [/delayload](../../build/reference/delayload-delay-load-import.md):`dllname` 링커 옵션입니다. 자체 버전의 도우미 함수를 사용하려는 경우가 아니면 delayimp.lib(데스크톱 응용 프로그램) 또는 dloadhelper.lib(스토어 앱)를 사용하여 프로그램을 연결해야 합니다.  
  
 다음은 DLL 지연 로드의 간단한 예입니다.  
  
```  
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll  
#include <windows.h>  
// uncomment these lines to remove .libs from command line  
// #pragma comment(lib, "delayimp")  
// #pragma comment(lib, "user32")  
  
int main() {  
   // user32.dll will load at this point  
   MessageBox(NULL, "Hello", "Hello", MB_OK);  
}  
```  
  
 프로젝트의 디버그 버전을 빌드합니다. 디버거를 사용하여 코드를 단계별로 이동하면 user32.dll이 `MessageBox`를 호출할 때만 로드된다는 것을 알 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)