---
title: 새 사용자 지정 또는 데이터 리소스 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- custom resources [C++]
- data resources [C++]
- resources [Visual Studio], creating
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 82d68ec7c9580cf1b95d4c678c491c4e33d12e10
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650848"
---
# <a name="creating-a-new-custom-or-data-resource"></a>새 사용자 지정 또는 데이터 리소스 만들기
프로젝트를 마우스 오른쪽 단추로 클릭 하 여 기본 리소스 스크립트 (.rc) 파일 구문을 사용 하 여 별도 파일에 다음 파일을 포함 하는 리소스를 배치 하 여 새 사용자 지정 또는 데이터 리소스를 만들 수 있습니다 **솔루션 탐색기** 클릭 **리소스 포함** 바로 가기 메뉴.  
  
### <a name="to-create-a-new-custom-or-data-resource"></a>새 사용자 지정 또는 데이터 리소스를 만들려면  
  
1. 사용자 지정 또는 데이터 리소스가 포함된[.rc 파일을 만듭니다](../windows/how-to-create-a-resource-script-file.md) .  
  
     null로 끝나는 따옴표가 붙은 문자열이나 10진수, 16진수 또는 8진수 형식의 정수로 .rc 파일의 사용자 지정 데이터를 입력할 수 있습니다.  
  
2.  **솔루션 탐색기**에서 프로젝트의 .rc 파일을 마우스 오른쪽 단추로 클릭한 후 바로 가기 메뉴에서 **리소스 내용** 을 클릭합니다.  
  
3.  에 **컴파일 시간 지시문** 상자에 입력을 `#include` 문을 사용자 지정 리소스를 포함 하는 파일의 이름을 제공 하는 합니다. 예를 들어:  
  
 ```cpp  
    #include mydata.rc  
 ```  
  
     입력한 구문 및 맞춤법이 정확한지 확인합니다. **컴파일 타임 지시문** 상자의 내용은 입력한 대로 정확하게 리소스 스크립트 파일에 삽입됩니다.  
  
4.  **확인** 을 클릭하여 변경 내용을 기록합니다.  
  
 사용자 지정 리소스를 만드는 또 다른 방법은 사용자 지정 리소스와 같이 외부 파일을 가져오는 것입니다. 자세한 내용은 [리소스 가져오기 및 내보내기](../windows/how-to-import-and-export-resources.md)를 참조하세요.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [Binary Editor](binary-editor.md)