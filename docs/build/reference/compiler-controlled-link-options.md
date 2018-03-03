---
title: "컴파일러 제어 LINK 옵션 | Microsoft Docs"
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
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc899fc7f1fc8c1805648e72e14ef13853841c90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options
/C 옵션을 지정 하지 않으면 CL 컴파일러 링크를 자동으로 호출 합니다. CL에서는 링커 명령줄 옵션 및 인수를 제어할 수 있습니다. 다음 표에서 연결에 영향을 주는 CL 기능을 요약 합니다.  
  
|CL 사양|링크에 영향을 주는 CL 작업|  
|----------------------|---------------------------------|  
|.C,.cxx,.cpp 또는.def 이외의 모든 파일 이름 확장명|파일 이름을 링크에 대 한 입력으로 전달합니다.|  
|*filename*.def|/DEF 전달:*filename*.def|  
|/F*번호*|/STACK 전달:*번호*|  
|/Fd*파일 이름*|/PDB 전달:*파일 이름*|  
|/Fe*파일 이름*|전달/출력:*파일 이름*|  
|/Fm*파일 이름*|전달 /MAP:*파일 이름*|  
|/Gy|패키지 함수를 만들어 (Comdat); 함수 수준 링크 사용|  
|/LD|/DLL 전달|  
|/LDd|/DLL 전달|  
|/link|명령줄의 나머지 부분을 LINK에 전달합니다.|  
|/MD 또는 /MT|.Obj 파일에 기본 라이브러리 이름을 배치합니다|  
|/Mdd 또는 /MTd|.Obj 파일에 기본 라이브러리 이름을 배치합니다. 기호를 정의 **_DEBUG**|  
|/nologo|/NOLOGO 전달|  
|/Zd|/DEBUG 전달|  
|/Zi 또는 /Z7|/DEBUG 전달|  
|/Zl|.Obj 파일에서 기본 라이브러리 이름 생략|  
  
 자세한 내용은 [컴파일러 옵션](../../build/reference/compiler-options.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)