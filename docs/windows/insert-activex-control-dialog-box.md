---
title: ActiveX 컨트롤 삽입 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.insertActiveXControls
dev_langs:
- C++
helpviewer_keywords:
- Insert ActiveX Control dialog box
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: 06638ea3-0726-40da-a989-9b89292d0e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0201619d463d677eae312d70a543a19887dbdb40
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011792"
---
# <a name="insert-activex-control-dialog-box"></a>ActiveX 컨트롤 삽입 대화 상자
이 대화 상자를 사용 하면 수 있습니다 [대화 상자에 ActiveX 컨트롤 삽입](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md) 사용 하는 동안 합니다 [대화 상자 편집기](../windows/dialog-editor.md)합니다.  
  
### <a name="activex-control"></a>ActiveX 컨트롤 
 Activex 컨트롤의 목록을 표시합니다. 이 대화 상자에서 컨트롤을 삽입 하는 래퍼 클래스를 생성 하지 않습니다. 래퍼 클래스를 해야 하는 경우 사용 하 여 [클래스 뷰](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) 만들려면 (자세한 내용은 참조 하십시오 [클래스를 추가](../ide/adding-a-class-visual-cpp.md)). 이 대화 상자에서 Activex 컨트롤을 없으면 공급 업체의 지침에 따라 컨트롤을 설치 하십시오.  
  
### <a name="path"></a>Path  
 ActiveX 컨트롤은 찾을 수 있는 파일이 표시 됩니다.  
  
 컨트롤을 배치할 수 있습니다는 **도구 상자** 창에 쉽게 액세스할 수 있도록 합니다. 자세한 내용은 [도구 상자 사용자 지정 대화 상자](http://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [도구 상자, 대화 상자 편집기 탭](../windows/dialog-editor-tab-toolbox.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)