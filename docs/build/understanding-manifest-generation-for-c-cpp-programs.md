---
title: "C/c + + 프로그램에 대 한 매니페스트 생성 이해 | Microsoft Docs"
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
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 848b4b449fa2c9c8930a616b70a5b61cb28d8fbf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ 프로그램의 매니페스트 생성 이해
A [매니페스트](http://msdn.microsoft.com/library/aa375365) 외부 XML 파일 또는 리소스가 제공 되는 XML 문서에 포함 된 응용 프로그램 또는 어셈블리. 매니페스트는 [응용 프로그램 격리](http://msdn.microsoft.com/library/aa375190) 이름 및 버전을 응용 프로그램에서 런타임에 바인딩해야 하는 공유 side-by-side-어셈블리의 관리 하는 데 사용 됩니다. Side-by-side-어셈블리의 매니페스트는 이름, 버전, 리소스 및 다른 어셈블리에 종속성을 지정 합니다.  
  
 격리 된 응용 프로그램 또는 side-by-side-어셈블리에 대 한 매니페스트를 만드는 두 가지가 있습니다. 첫째, 어셈블리를 만든 사람 명명 요구 사항 및 규칙에 매니페스트 파일을 수동으로 만들 수 있습니다. 또는 프로그램이 CRT, MFC, ATL 같은 Visual c + + 어셈블리에 의존 하는 경우 다음 매니페스트 수 수 자동으로 생성 링커.  
  
 어셈블리 정보를 포함 하는 Visual c + + 라이브러리의 헤더 및이 어셈블리 정보를 최종 이진에 대 한 매니페스트를 만드는 데 사용할 링커에 의해 때 포함 됩니다. 링커는 이진 매니페스트 파일이 포함 되어 있지 않으며만 외부 파일로 매니페스트를 생성할 수 있습니다. 모든 시나리오에 대 한 외부 파일로 매니페스트 있으면 작동 하지 않습니다. 예를 들어 전용 어셈블리 매니페스트 포함 하는 것이 좋습니다. Nmake를 사용 하 여 코드를 빌드하는 것과 같은 명령줄 빌드에서 매니페스트 포함 될 수 있습니다; 매니페스트 도구를 사용 하 여 자세한 내용은 참조 [명령줄에서 매니페스트 생성](../build/manifest-generation-at-the-command-line.md)합니다. 빌드하는 경우 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], 매니페스트 도구에 대 한 속성을 설정 하 여 매니페스트를 포함할 수는 **프로젝트 속성** 대화; 참조 하십시오 [Visual Studio에서 매니페스트 생성](../build/manifest-generation-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [격리 된 응용 프로그램 및 side-by-side-어셈블리의 개념](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)