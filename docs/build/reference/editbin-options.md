---
title: "EDITBIN 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EDITBIN 프로그램, 옵션"
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EDITBIN 옵션
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

EDITBIN을 사용하여 개체 파일, 실행 파일 및 DLLs\(동적 연결 라이브러리\)을 수정할 수 있습니다.  EDITBIN을 사용 하면 변경 옵션을 지정 합니다.  
  
 옵션은 옵션 지정자\(대시\( \- \) 또는 슬래시\( \/ \) 중 하나\)와 그 다음에 나오는 옵션 이름으로 구성됩니다.  옵션 이름은 약식으로 표기할 수 없습니다.  일부 옵션에서는 콜론\( : \) 다음에 인수를 지정합니다.  옵션 사양에는 공백이나 탭을 사용할 수 없습니다.  한 개 이상의 공백 또는 탭을 사용하여 명령줄에서 옵션 사양을 구분합니다.  옵션 이름 및 그 키워드 또는 파일 이름 인수는 대\/소문자를 구분하지 않습니다.  예를 들어,\-바인딩 및 \/bind 수정 같은 것을 의미 합니다.  
  
 EDITBIN에는 다음과 같은 옵션이 있습니다.  
  
|옵션|용도|  
|--------|--------|  
|[\/ALLOWBIND](../../build/reference/allowbind.md)|DLL을 다시 실행할 것인지를 지정합니다.|  
|[\/ALLOWISOLATION](../../build/reference/allowisolation.md)|DLL 또는 실행 파일의 매니페스트 조회 동작을 지정합니다.|  
|[\/APPCONTAINER](../../build/reference/appcontainer.md)|예를 들어 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]와 같이 응용 프로그램을 appcontainer 프로세스 환경 내에서 실행해야 하는지 여부를 지정합니다.|  
|[\/BIND](../../build/reference/bind.md)|로드 시간이 속도를 지정 된 개체의 진입점 주소를 설정합니다.|  
|[\/DYNAMICBASE](../../build/reference/dynamicbase.md)|로드할 때 의 ASLR\(Address Space Layout Randomization\) 기능을 사용하여 임의로 DLL기준 주소를 지정할 수 있는 실행 가능 이미지를 생성할지 여부를 지정합니다.|  
|[\/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|내부 링커 오류를 Microsoft에 보고합니다.|  
|[\/HEAP](../../build/reference/heap.md)|힙의 실행 파일 이미지의 크기를 바이트 단위로 설정합니다.|  
|[\/HIGHENTROPYVA](../../build/reference/highentropyva.md)|DLL 또는 실행 파일 이미지가 높은 엔트로피 64비트 ASLR\(Address Space Layout Randomization\)을 지원하는지 여부를 지정합니다.|  
|[\/INTEGRITYCHECK](../../build/reference/integritycheck.md)|로드할 때 디지털 서명을 확인할 지 여부를 지정 합니다.|  
|[\/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|개체는 2gb 이상의 주소를 지원 하는지 여부를 지정 합니다.|  
|[\/NOLOGO](../../build/reference/nologo-editbin.md)|EDITBIN 시작 배너를 표시하지 않습니다.|  
|[\/NXCOMPAT](../../build/reference/nxcompat.md)|실행 가능 이미지 Windows 데이터 실행 방지 기능과 호환 되는지 여부를 지정 합니다.|  
|[\/REBASE](../../build/reference/rebase.md)|지정된 개체에 대 한 기준 주소를 설정합니다.|  
|[\/RELEASE](../../build/reference/release.md)|.exe 헤더의 체크섬을 설정합니다.|  
|[\/SECTION](../../build/reference/section-editbin.md)|섹션의 특성을 재정의합니다.|  
|[\/STACK](../../build/reference/stack.md)|stack의 실행 파일 이미지의 크기를 바이트 단위로 설정합니다.|  
|[\/SUBSYSTEM](../../build/reference/subsystem.md)|실행 환경을 지정합니다.|  
|[\/SWAPRUN](../../build/reference/swaprun.md)|실행 파일 이미지를 스왑 파일로 복사하고 다음에서 실행해야 하는 것을 지정 합니다.|  
|[\/TSAWARE](../../build/reference/tsaware.md)|응용 프로그램은 다중 사용자 환경에서 실행 하도록 지정합니다.|  
|[\/VERSION](../../build/reference/version.md)|헤더에 버전 번호를 설정 합니다.|  
  
## 참고 항목  
 [C\/C\+\+ 빌드 도구](../../build/reference/c-cpp-build-tools.md)   
 [EDITBIN 참조](../../build/reference/editbin-reference.md)