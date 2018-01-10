---
title: "모듈 정의 (합니다. Def) 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49f5eb5b75bad22b59cb4fbb98554bbfd44d13b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="module-definition-def-files"></a>모듈 정의(.Def) 파일
모듈 정의 (.def) 파일 링커 내보내기, 특성 및 연결 될 프로그램에 대 한 기타 정보에 대 한 정보를 제공 합니다. .Def 파일 DLL을 빌드할 때 가장 유용 합니다. 있기 때문에 [링커 옵션](../../build/reference/linker-options.md) 사용할 수 있는 모듈 정의 문의 대신.def 파일은 일반적으로 불필요 합니다. 사용할 수도 있습니다 [__declspec (dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) 지정 하는 방법으로 함수를 내보냈습니다.  
  
 링커 단계.def 파일을 호출할 수 있습니다는 [/DEF (모듈 정의 파일 지정)](../../build/reference/def-specify-module-definition-file.md) 링커 옵션입니다.  
  
 내보내기가 없는.exe 파일을 작성 하는.def 파일을 사용 하 여 출력 파일 크고 속도가 느립니다 로드가 생성 됩니다.  
  
 예를 들어 참조 [DLL를 사용 하 여 DEF 파일에서 내보내는](../../build/exporting-from-a-dll-using-def-files.md)합니다.  
  
 자세한 내용은 다음 섹션을 참조 하십시오.  
  
-   [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [EXPORTS](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [LIBRARY](../../build/reference/library.md)  
  
-   [이름](../../build/reference/name-c-cpp.md)  
  
-   [섹션](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [STUB](../../build/reference/stub.md)  
  
-   [버전](../../build/reference/version-c-cpp.md)  
  
-   [예약 된 단어](../../build/reference/reserved-words.md)  
  
## <a name="see-also"></a>참고 항목  
 [C/C++ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [링커 옵션](../../build/reference/linker-options.md)  