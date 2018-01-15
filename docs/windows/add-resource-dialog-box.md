---
title: "리소스 추가 대화 상자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.insertresource
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio], adding
- Add Resource dialog box
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fde90f5d7c7822155e36b77c74cd80cdf56b10d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="add-resource-dialog-box"></a>리소스 추가 대화 상자
이 대화 상자는 C++ Windows 데스크톱 응용 프로그램 프로젝트에 리소스를 추가하는 데 사용합니다.  
  
> [!NOTE]
>  이 정보는 Windows 스토어 앱의 리소스에 적용되지 않습니다. 참조 하는 방법에 대 한 자세한 내용은 [앱 리소스 정의](http://msdn.microsoft.com/en-us/476ea844-632c-4467-9ce3-966be1350dd4)합니다.  
  
 **리소스 종류**  
 만들려는 리소스의 종류를 지정합니다.  
  
 커서와 대화 상자 리소스 범주를 확장하여 추가 리소스를 표시할 수 있습니다. 이러한 리소스가...\Microsoft Visual Studio에에서 있는 `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct 합니다. .Rct 파일을 추가 하려면,이 디렉터리에 저장 해야 하거나 지정 해야 합니다는 [포함 경로](../windows/how-to-specify-include-directories-for-resources.md) 하 합니다. 그러면 이러한 파일의 리소스가 해당 범주의 두 번째 수준에 표시됩니다. 추가할 수 있는 .rct 파일의 수는 미리 설정된 제한이 없습니다.  
  
 트리 컨트롤의 최상위 수준에 있는 리소스는 Visual Studio에서 제공하는 기본 리소스입니다.  
  
 **새로 만들기**  
 선택한 형식을 기반으로 리소스를 만듭니다는 **리소스 종류** 상자입니다. 리소스가 해당 편집기에서 열립니다. 예를 들어 대화 상자 리소스를 만드는 경우에서 열립니다는 [대화 상자 편집기](../windows/dialog-editor.md)합니다.  
  
 **Import**  
 열립니다는 **가져올** 현재 프로젝트로 가져올 하려는 대화 상자를 이동할 수는 리소스에 있습니다. 비트맵, 아이콘, 커서, HTML 리소스 파일, 사운드(.WAV) 리소스 파일 또는 사용자 지정 리소스 파일을 가져올 수 있습니다.  
  
 **사용자 지정**  
 열립니다는 [새 사용자 지정 리소스 대화 상자](../windows/new-custom-resource-dialog-box.md) 사용자 지정 리소스를 만들 수 있는 합니다. 사용자 지정 리소스는 바이너리 편집기에서만 편집할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [방법: 리소스 파일 만들기](../windows/how-to-create-a-resource.md)