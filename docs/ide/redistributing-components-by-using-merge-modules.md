---
title: "병합 모듈을 사용 하 여 구성 요소 재배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 093c732563844b14a3f99662150d4db9b2fac1fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-components-by-using-merge-modules"></a>병합 모듈을 사용하여 구성 요소 재배포
Visual Studio에 포함 되어 [병합 모듈](http://msdn.microsoft.com/library/aa367434) 응용 프로그램과 함께 재배포할 수 허가 된 사용자는 각 Visual c + + 구성 요소에 대 한 합니다. 병합 모듈이 Windows Installer 설치 파일에서 컴파일되면 특정 플랫폼이 있는 컴퓨터에 특정 DLL을 배포할 수 있습니다. 설치 파일에서 병합 모듈을 응용 프로그램의 필수 구성 요소로 지정합니다. 병합 모듈이 files\common Files\Merge 모듈 설치 된 Visual Studio가 설치 된 경우\\합니다. (Visual c + + Dll의 디버그가 아닌 버전에만 재배포할 수 있습니다.) 자세한 내용 및 재배포에 대 한 라이선스가 있는 병합 모듈의 목록에 대 한 링크에 대 한 참조 [Visual c + + 파일 재배포](../ide/redistributing-visual-cpp-files.md)합니다.  
  
 재배포 가능한 Visual c + + Dll을 %SYSTEMROOT%\system32\ 폴더에 설치를 사용 하도록 설정 하려면 병합 모듈을 사용할 수 있습니다. (Visual Studio 자체에이 방법을 사용합니다.) 그러나 설치하는 사용자가 관리자 권한이 없는 경우 이 폴더에 설치되지 않습니다.  
  
 응용 프로그램을 제공할 필요가 없고 둘 이상의 DLL 버전에 대한 종속성이 없는 경우를 제외하고 병합 모듈을 사용하지 않는 것이 좋습니다. 동일한 DLL의 여러 버전에 대한 병합 모듈은 하나의 설치 관리자에 포함될 수 없고 병합 모듈은 응용 프로그램에 관계없이 DLL을 제공하기 어렵습니다. 대신, Visual c + + 재배포 가능 패키지를 설치 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 파일 재배포](../ide/redistributing-visual-cpp-files.md)