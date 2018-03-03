---
title: "지연 로드 된 DLL에 대 한 모든 가져오기 로드 | Microsoft Docs"
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
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8afa206e62702407d9974802f9422c8597d772ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>지연 로드된 DLL에 대한 모든 가져오기 로드
**__HrLoadAllImportsForDll** delayhlp.cpp에 정의 된 함수를 사용 하 여 지정 된 DLL에서 모든 가져오기 로드 하면 링커에서 [/delayload](../../build/reference/delayload-delay-load-import.md) 링커 옵션입니다.  
  
 모든 가져오기 로드를 사용 하면 코드의 한 곳에서 오류 처리 및 예외 처리 imports에 대 한 실제 호출을 사용할 필요가 수 있습니다. 또한 가져오기를 로드에 실패 하는 도우미 코드의 결과 프로세스를 통해 응용 프로그램을 부분적으로 실패 하는 상황을 방지할 수 있습니다.  
  
 호출 **__HrLoadAllImportsForDll** 후크 및 오류의 동작 변경 되지 않습니다 참조 처리; [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md) 자세한 정보에 대 한 합니다.  
  
 DLL 이름에 전달 된 **__HrLoadAllImportsForDll** DLL 자체 내에 저장 하는 이름을 비교 되 고 대/소문자 구분 합니다.  
  
 다음 예제에서는 호출 하는 방법을 보여 줍니다. **__HrLoadAllImportsForDll**:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)