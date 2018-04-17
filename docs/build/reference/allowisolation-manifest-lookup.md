---
title: -/ALLOWISOLATION (매니페스트 조회) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0ca939021a6fc530b11c6ec66fc74cc012da1c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION(매니페스트 조회)
매니페스트 조회 동작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>설명  
 **/ALLOWISOLATION:NO** 매니페스트가 없었던 마치 Dll이 로드 된 나타냅니다 링커가 설정 하 고는 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` 선택적 헤더의 비트 `DllCharacteristics` 필드입니다.  
  
 **/ALLOWISOLATION** 조회 및 로드가 매니페스트 하 운영 체제.  
  
 **/ALLOWISOLATION** 값이 기본값입니다.  
  
 실행 파일에 대 한 격리가 비활성화 되었으면, Windows 로더가 새로 생성된 된 프로세스에 대 한 응용 프로그램 매니페스트를 찾으려고 시도 하지 않습니다. 새 프로세스는 기본 활성화 컨텍스트가 갖습니다 실행 파일 또는 이름 가진 실행 파일과 동일한 디렉터리에 배치 된 내부 매니페스트 경우에 *실행 파일 이름***. exe.manifest**합니다.  
  
 자세한 내용은 참조 [매니페스트 파일 참조](http://msdn.microsoft.com/library/aa375632)합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **매니페스트 파일** 속성 페이지.  
  
5.  수정 된 **격리 허용** 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)