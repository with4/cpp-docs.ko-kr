---
title: 리소스 미리 보기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8393988bf6d831c8b9718d6685785d523303f3fa
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016407"
---
# <a name="previewing-resources"></a>리소스 미리 보기
리소스 미리 보기를 사용 하면 그래픽 리소스를 열지 않고 볼 수 있습니다. 리소스 식별자를 숫자로 변경 되므로 컴파일된 한 후에 미리 보기는 실행 파일에 대 한 유용 합니다. 종종 이러한 숫자 식별자는 충분 한 정보를 제공 하지 않습니다, 이후 리소스를 미리 보기 사용 하면 신속 하 게 식별할 수 있습니다.  
  
 다음 리소스 종류의 시각적 레이아웃을 미리 볼 수 있습니다.  
  
-   Bitmap  
  
-   대화 상자  
  
-   아이콘  
  
-   메뉴  
  
-   Cursor  
  
-   Toolbar  
  
 Visual 미리 보기 함수 가속기, 매니페스트, 문자열 테이블 및 버전 정보 리소스에 적용 되지 않습니다.  
  
### <a name="to-preview-resources"></a>리소스를 미리 보려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md) 또는 문서 창에 예를 들어, 리소스 선택 **IDD_ABOUTBOX**합니다.  
  
     > [!NOTE]
     > 프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window)를 클릭 합니다 **속성 페이지** 단추입니다.  
  
     \- 또는 -  
  
3.  에 **뷰** 메뉴에서 클릭 **속성 페이지**합니다.  
  
     합니다 **속성 페이지** 열리고 리소스에 대 한 해당 리소스의 미리 보기를 표시 합니다. 사용할 수 있습니다 합니다 **위로** 및 **아래로** 에서 트리를 탐색 하려면 화살표 키를 제어할 **리소스 뷰** 나 문서 창을 합니다. 합니다 **속성 페이지** 개방 하며에 포커스가 생기 며 미리 볼 수 있는 모든 리소스를 표시 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항 
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로젝트 외부에서 리소스 스크립트 파일 열기(독립 실행형)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
 [리소스 편집기](../windows/resource-editors.md)