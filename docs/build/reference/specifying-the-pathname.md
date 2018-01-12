---
title: "경로 이름 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2412ab15317604e1d6cccc5535226d429d8ba6b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-pathname"></a>경로 이름 지정
각 출력 파일 옵션을 *pathname* 인수를 위치와 출력 파일에 대 한 이름을 지정할 수 있습니다. 인수는 드라이브 이름, 디렉터리 및 파일 이름에 포함할 수 있습니다. 옵션 및 인수 사이 공백이 없어야 합니다.  
  
 경우 *pathname* 파일 이름을 포함 한 확장명 없이 컴파일러 출력 기본 확장명을 사용 합니다. 경우 *pathname* 파일 이름 없이 디렉터리만 포함 되어 컴파일러는 기본 이름이 지정된 된 디렉터리에서 파일을 만듭니다. 기본 이름은 원본 파일과 출력 파일의 형식을 기반으로 기본 확장 프로그램의 기본 이름을 기반으로 합니다. 두면 *pathname* 완전히 컴파일러 기본 디렉터리에 기본 이름으로 파일을 만듭니다.  
  
 또는 *pathname* 인수는 파일 이름 대신 장치 이름을 (AUX, CON, PRN, 또는 NUL) 될 수 있습니다. 장치 이름의 일부로 옵션 및 장치 이름이 나 콜론 사이 공백을 넣지 마십시오.  
  
|장치 이름|내용|  
|-----------------|----------------|  
|AUX|보조 장치|  
|CON|콘솔|  
|PRN|프린터|  
|NUL|Null 장치 (파일 생성)|  
  
## <a name="example"></a>예  
 다음 명령줄 프린터 맵 파일을 보냅니다.  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)