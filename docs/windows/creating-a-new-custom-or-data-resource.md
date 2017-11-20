---
title: "새 사용자 지정 또는 데이터 리소스 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.binary
dev_langs: C++
helpviewer_keywords:
- custom resources [C++]
- data resources [C++]
- resources [Visual Studio], creating
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff1beb01e08ea78f96b7f161e7f3ffc1110ff63b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-new-custom-or-data-resource"></a>새 사용자 지정 또는 데이터 리소스 만들기
기본 리소스 스크립트(.rc) 파일 구문을 사용하여 별도의 파일에 리소스를 배치한 후 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **리소스 내용** 을 클릭하여 해당 파일을 포함함으로써 새 사용자 지정 또는 데이터 리소스를 만들 수 있습니다.  
  
### <a name="to-create-a-new-custom-or-data-resource"></a>새 사용자 지정 또는 데이터 리소스를 만들려면  
  
1. 사용자 지정 또는 데이터 리소스가 포함된[.rc 파일을 만듭니다](../windows/how-to-create-a-resource-script-file.md) .  
  
     null로 끝나는 따옴표가 붙은 문자열이나 10진수, 16진수 또는 8진수 형식의 정수로 .rc 파일의 사용자 지정 데이터를 입력할 수 있습니다.  
  
2.  **솔루션 탐색기**에서 프로젝트의 .rc 파일을 마우스 오른쪽 단추로 클릭한 후 바로 가기 메뉴에서 **리소스 내용** 을 클릭합니다.  
  
3.  **컴파일 타임 지시문** 상자에, 사용자 지정 리소스를 포함하는 파일의 이름을 지정하는 **#include** 문을 입력합니다. 예:  
  
 ```  
    #include mydata.rc  
 ```  
  
     입력한 구문 및 맞춤법이 정확한지 확인합니다. **컴파일 타임 지시문** 상자의 내용은 입력한 대로 정확하게 리소스 스크립트 파일에 삽입됩니다.  
  
4.  **확인** 을 클릭하여 변경 내용을 기록합니다.  
  
 사용자 지정 리소스를 만드는 또 다른 방법은 사용자 지정 리소스와 같이 외부 파일을 가져오는 것입니다. 자세한 내용은 [리소스 가져오기 및 내보내기](../windows/how-to-import-and-export-resources.md)를 참조하세요.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](https://msdn.microsoft.com/library/f45fce5x.aspx) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](https://msdn.microsoft.com/library/xbx3z216.aspx)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](https://msdn.microsoft.com/library/h6270d0z.aspx)합니다.  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [Binary Editor](binary-editor.md)

