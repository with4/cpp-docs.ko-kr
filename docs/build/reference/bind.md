---
title: -BIND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /bind
dev_langs: C++
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64d3269bda732ad16941a433674ed1c1ec2bf6e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="bind"></a>/BIND
```  
/BIND[:PATH=path]  
```  
  
## <a name="remarks"></a>설명  
 이 옵션은 실행 파일 또는 DLL에 대 한 가져오기 주소 테이블에서 진입점의 주소를 설정합니다. 프로그램의 로드 시간을 줄이려면이 옵션을 사용 합니다.  
  
 프로그램의 실행 파일 및 Dll에 지정 된 *파일* EDITBIN 명령줄의 인수입니다. 선택적 *경로* 인수 /BIND에 지정된 된 파일에서 사용 하는 Dll의 위치를 지정 합니다. 여러 디렉터리는 세미콜론으로 구분 (**;**). 경우 *경로* 를 지정 하지 않으면 EDITBIN PATH 환경 변수에 지정 된 디렉터리를 검색 합니다. 경우 *경로* 지정 EDITBIN PATH 변수를 무시 합니다.  
  
 기본적으로 프로그램 로더는 프로그램을 로드할 때 진입점의 주소를 설정 합니다. 이 프로세스는 시간 여러 Dll 진입점 프로그램에서 참조의 수에 따라 달라 집니다. 프로그램 /BIND, 되었고 실행 파일에 대 한 기본 주소 및 그 Dll 이미 로드 된 Dll와 충돌 하지 않는 경우 운영 체제가이 주소를 설정할 필요 하지 않습니다. 파일 하지 기반 잘못 된 경우에는 운영 체제에서 프로그램의 Dll를 뒤로 다시 지정 및 진입점 주소를 프로그램의 로드 시간에 다시 계산 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)