---
title: "기본 ATL 프로젝트 구성 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, default configurations
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 41ab65c411bef478d063e5165d3167f58ace37d7
ms.lasthandoff: 02/24/2017

---
# <a name="default-atl-project-configurations"></a>기본 ATL 프로젝트 구성
이 항목에서는 Visual c + + 6.0에 기본 프로젝트 구성과 함께 Visual c + +.NET의 기본 ATL 프로젝트 구성을 비교 합니다.  
  
## <a name="visual-c-net-default-configurations"></a>Visual c + +.NET 기본 구성  
 Visual c + +.net에서는 ATL 프로젝트 마법사에서 기본적으로 두 가지 프로젝트 구성을 만듭니다.  
  
### <a name="visual-c-net-configurations"></a>Visual c + +.NET 구성  
  
|구성|문자 집합입니다.|ATL 사용|  
|-------------------|-------------------|----------------|  
|릴리스|MBCS|DLL|  
|디버그|MBCS|DLL|  
  
 **문자 집합**, **ATL 사용** 및 모두에 변경할 수는 **프로젝트 설정** 대화 상자의 **일반** 탭 합니다. 구성 관리자를 사용 하 여 자신만 구성을 추가할 수도 있습니다. 자세한 내용은 다음을 참조 하십시오. [빌드 구성](/visualstudio/ide/understanding-build-configurations)합니다.  
  
## <a name="version-60-default-configurations"></a>버전 6.0 기본 구성  
 Visual c + + 버전 6.0의 ATL COM 응용 프로그램 마법사 (이제 ATL 프로젝트 마법사)는 기본적으로 6 개의 프로젝트 구성을 만들었습니다. 구성을은 릴리스, 디버그, 유니코드 및 CRT 및 ATL 설정을 사용 하 여 다양 하 게 변형 되었습니다. 이러한 모든 구성 하도록 선택할 경우 Configuration Manager를 사용 하 여 Visual c + +.NET에서 복제할 수 있습니다.  
  
### <a name="version-60-configurations"></a>버전 6.0 구성  
  
|구성|문자 집합입니다.|ATL 사용|  
|-------------------|-------------------|----------------|  
|디버그|MBCS|정적|  
|유니코드를 디버그 합니다.|유니코드|정적|  
|릴리스 최소 종속성|MBCS|정적|  
|릴리스 최소 종속성 유니코드|유니코드|정적|  
|릴리스 최소 크기|MBCS|DLL|  
|최소 크기 유니코드를 해제 합니다.|유니코드|DLL|  
  
## <a name="see-also"></a>참고 항목  
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)   
 [구성 관리자 대화 상자](http://msdn.microsoft.com/en-us/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [컴파일 및 빌드](/visualstudio/ide/compiling-and-building-in-visual-studio)


