---
title: /APPCONTAINER (UWP/Microsoft 스토어 앱) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca1a3ed5adaada689d374eeb3e67bae6c989e0b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369294"
---
# <a name="appcontainer-microsoft-store-app"></a>/APPCONTAINER (Microsoft 스토어 앱)
링커 앱 컨테이너에서 실행 해야 하는 실행 가능 이미지를 만들지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>설명  
 /APPCONTAINER는 기본적으로 해제 되어 있습니다.  
  
 이 옵션을 appcontainer 프로세스 격리 환경에서 앱을 실행 해야 하는지 여부를 나타내는 실행 파일을 수정 합니다. /APPCONTAINER appcontainer 환경에서 실행 되어야 하는 응용 프로그램에 대 한 지정-예를 들어는 유니버설 Windows 플랫폼 (UWP) 또는 Windows Phone 8.x 앱. (옵션은 자동으로 설정 Visual Studio에서 서식 파일에서 유니버설 Windows 앱을 만들 때.) 데스크톱 응용 프로그램에 대 한 /APPCONTAINER:NO 지정 하거나만 옵션을 생략 합니다.  
  
 /APPCONTAINER 옵션에 도입 된 [!INCLUDE[win8](../../build/reference/includes/win8_md.md)]합니다.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **명령줄** 속성 페이지.  
  
5.  **추가 옵션**, 입력 `/APPCONTAINER` 또는 `/APPCONTAINER:NO`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)