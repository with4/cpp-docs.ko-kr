---
title: "LINK 환경 변수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67b36afce92140c4f205f8e5a4a46dfc7ac2d300
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="link-environment-variables"></a>LINK 환경 변수

LINK 도구는 다음과 같은 환경 변수를 사용합니다.  
  
-   링크 및 \_링크\_에 정의 합니다. 인수에 정의 된 링크 도구 옵션 및 LINK 환경 변수에서 정의 된 인수 앞에 추가 하 고 옵션을 추가 하 고는 \_링크\_ 환경 변수를 처리 하기 전에 명령줄 인수입니다.  
  
-   LIB(정의된 경우). LINK 도구는 개체, 라이브러리 또는 명령줄에서 또는 지정 된 기타 파일을 검색할 때 LIB 경로 사용는 [/base](../../build/reference/base-base-address.md) 옵션입니다. 또한 LIB 경로를 사용하여 개체에 명명된 .pdb 파일을 찾습니다. LIB 변수에는 하나 이상의 경로 사양이 세미콜론으로 구분되어 포함될 수 있습니다. 한 경로는 Visual C++ 설치의 \lib 하위 디렉터리를 가리켜야 합니다.  
  
-   PATH(도구가 CVTRES를 실행해야 하고 LINK 자체와 동일한 디렉터리에서 파일을 찾을 수 없는 경우). LINK가 .res 파일을 연결하려면 CVTRES가 필요합니다. PATH는 Visual C++ 설치의 \bin 하위 디렉터리를 가리켜야 합니다.  
  
-   TMP(OMF 또는 .res 파일을 연결할 때 디렉터리 지정)  
  
## <a name="see-also"></a>참고 항목  

[링커 옵션 설정](../../build/reference/setting-linker-options.md)   
[링커 옵션](../../build/reference/linker-options.md)   
[명령줄에서 C/C++ 코드 빌드](../../build/building-on-the-command-line.md)  
[명령줄 빌드에 맞는 경로 및 환경 변수 설정](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
