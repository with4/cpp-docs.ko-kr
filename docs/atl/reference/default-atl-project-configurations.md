---
title: "기본 ATL 프로젝트 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 기본 구성"
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 기본 ATL 프로젝트 구성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 Visual C\+\+ .NET의 기본 ATL 프로젝트 구성과 Visual C\+\+ 6.0의 기본 프로젝트 구성을 비교합니다.  
  
## Visual C\+\+ .NET 기본 구성  
 Visual C\+\+ .NET의 ATL 프로젝트 마법사에서는 기본적으로 두 개의 프로젝트 구성을 만듭니다.  
  
### Visual C\+\+ .NET 구성  
  
|구성|문자 집합|ATL 사용|  
|--------|-----------|------------|  
|Release|MBCS|DLL|  
|디버그|MBCS|DLL|  
  
 **문자 집합** 및 **ATL 사용**은 모두 **프로젝트 설정** 대화 상자의 **일반** 탭에서 변경할 수 있습니다.  또한 구성 관리자를 사용하여 사용자 고유의 구성을 추가할 수도 있습니다.  자세한 내용은 [빌드 구성](../Topic/Understanding%20Build%20Configurations.md)을 참조하십시오.  
  
## 버전 6.0 기본 구성  
 Visual C\+\+ 버전 6.0의 ATL COM 응용 프로그램 마법사\(현재는 ATL 프로젝트 마법사\)에서는 기본적으로 여섯 개의 프로젝트 구성을 만들었습니다.  즉, 릴리스, 디버그, 유니코드, 그리고 CRT 및 ATL 설정의 사용에 따라 구성이 다양했습니다.  Visual C\+\+ .NET에서는 필요한 경우 구성 관리자를 사용하여 이 모든 구성을 복제할 수 있습니다.  
  
### 버전 6.0 구성  
  
|구성|문자 집합|ATL 사용|  
|--------|-----------|------------|  
|디버그|MBCS|Static|  
|디버그 유니코드|UNICODE|Static|  
|릴리스 최소 종속성|MBCS|Static|  
|릴리스 최소 종속성 유니코드|UNICODE|Static|  
|릴리스 최소 크기|MBCS|DLL|  
|릴리스 최소 크기 유니코드|UNICODE|DLL|  
  
## 참고 항목  
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)   
 [Configuration Manager Dialog Box](http://msdn.microsoft.com/ko-kr/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Visual Studio에서 응용 프로그램　빌드](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)