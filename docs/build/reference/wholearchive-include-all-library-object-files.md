---
title: "-WHOLEARCHIVE (모든 라이브러리 개체 파일 포함) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3499d6583c7d9801aa4c3b12c66196c975b192ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wholearchive-include-all-library-object-files"></a>/ WHOLEARCHIVE (모든 라이브러리 개체 파일 포함)
연결 된 실행 파일에서 정적 라이브러리의 모든 개체 파일을 포함 하도록 링커에 강제로 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
> / WHOLEARCHIVE [:*라이브러리*]  
  
## <a name="remarks"></a>설명  
  
/WHOLEARCHIVE 옵션에 지정된 된 정적 라이브러리에서 모든 개체 파일을 포함 하거나 명령 링크에 지정 된 모든 정적 라이브러리에서 없는 라이브러리를 지정 하는 경우 링커 강제로 수행 합니다. 여러 라이브러리에 대 한 /WHOLEARCHIVE 옵션을 지정 하려면 링커 명령줄에서 둘 이상의 /WHOLEARCHIVE 전환 사용할 수 있습니다. 기본적으로 링커는 실행 파일에 다른 개체 파일에서 참조 하는 기호를 내보내는 경우에 연결 된 출력에 파일 개체를 포함 합니다. /WHOLEARCHIVE 옵션을 링커 명령줄에서 개별적으로 지정 된 경우에 따라 정적 라이브러리에 보관 된 모든 개체 파일을 처리 하는 링커 선택 하면 됩니다.  
  
정적 라이브러리에서 모든 기호를 다시 내보낼 /WHOLEARCHIVE 옵션을 사용할 수 있습니다. 이렇게 하면 라이브러리 코드, 리소스 및 메타 데이터의 모든 포함 되는 둘 이상의 정적 라이브러리에서 구성 요소를 만들 때 있는지 확인 해야 합니다. 내보내기에 대 한 Windows 런타임 구성 요소를 포함 하는 경고 LNK4264 하는 정적 라이브러리를 만들 때 표시 되 면 해당 라이브러리를 다른 구성 요소나 응용 프로그램에 연결할 때 /WHOLEARCHIVE 옵션을 사용 합니다.  
  
/WHOLEARCHIVE 옵션은 Visual Studio 2015 업데이트 2에서 도입 되었습니다.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
1.  선택 된 **명령줄** 속성 페이지에서 **구성 속성**, **링커**합니다.  
  
1.  /WHOLEARCHIVE 옵션을 추가 하는 **추가 옵션** 입력란.  
  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)