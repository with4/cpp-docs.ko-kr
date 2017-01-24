---
title: "/BIND | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/bind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BIND editbin 옵션"
  - "BIND editbin 옵션"
  - "-BIND editbin 옵션"
  - "진입점"
  - "진입점, 주소"
  - "주소 테이블 가져오기"
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /BIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BIND[:PATH=path]  
```  
  
## 설명  
 이 옵션은 실행 파일 또는 DLL에 대한 가져오기 주소 테이블의 진입점 주소를 설정합니다.  이 옵션을 사용하면 프로그램 로드 시간이 줄어듭니다.  
  
 EDITBIN 명령줄에서 *files* 인수에 프로그램의 실행 파일 및 DLL을 지정합니다.  \/BIND의 선택적 인수인 *path*는 지정된 파일이 사용하는 DLL 위치를 지정합니다.  디렉터리가 여러 개인 경우 세미콜론\(**;**\)으로 구분합니다.  *path*를 지정하지 않은 경우 EDITBIN은 PATH 환경 변수에 지정된 디렉터리를 검색합니다.  *path*를 지정한 경우 EDITBIN은 PATH 변수를 무시합니다.  
  
 기본적으로 프로그램 로더는 프로그램을 로드할 때 진입점 주소를 설정합니다.  이 과정에 소요되는 시간은 프로그램에서 참조하는 DLL 수와 진입점 수에 따라 다릅니다.  프로그램이 \/BIND로 수정되었고 실행 파일 및 그 DLL의 기본 주소가 이미 로드된 DLL과 충돌하지 않는 경우 운영 체제에서 이 주소를 설정할 필요는 없습니다.  파일의 기본 주소가 잘못된 경우 운영 체제에서 프로그램의 DLL을 다시 배치하고 진입점 주소를 다시 계산하기 때문에 프로그램 로드 시간이 늘어납니다.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)