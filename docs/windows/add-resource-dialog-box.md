---
title: 리소스 추가 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.insertresource
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], adding
- Add Resource dialog box
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc7826b10e822b833b7a0a9361d55f74da46342a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651693"
---
# <a name="add-resource-dialog-box"></a>리소스 추가 대화 상자
이 대화 상자는 C++ Windows 데스크톱 응용 프로그램 프로젝트에 리소스를 추가하는 데 사용합니다.  
  
> [!NOTE]
>  이 정보는 유니버설 Windows 플랫폼 앱에서 리소스에 적용 되지 않습니다. 참조 하는 방법에 대 한 자세한 내용은 [앱 리소스 및 리소스 관리 시스템](/windows/uwp/app-resources/)입니다.  
  
### <a name="resource-type"></a>리소스 형식 
 만들려는 리소스의 종류를 지정합니다.  
  
 커서와 대화 상자 리소스 범주를 확장하여 추가 리소스를 표시할 수 있습니다. 이러한 리소스가 있는 Visual Studio...\Microsoft에서 `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct 합니다. .Rct 파일을 추가,이 디렉터리에 추가 해야 하거나 지정 해야 합니다는 [경로가 포함](../windows/how-to-specify-include-directories-for-resources.md) 에 있습니다. 그러면 이러한 파일의 리소스가 해당 범주의 두 번째 수준에 표시됩니다. 추가할 수 있는 .rct 파일의 수는 미리 설정된 제한이 없습니다.  
  
 트리 컨트롤의 최상위 수준에 있는 리소스는 Visual Studio에서 제공하는 기본 리소스입니다.  
  
### <a name="new"></a>새로 만들기
 선택한 형식에 따라 리소스를 만들어 합니다 **리소스 종류** 상자입니다. 리소스가 해당 편집기에서 열립니다. 예를 들어 대화 상자 리소스를 만드는 경우에서 열립니다는 [대화 상자 편집기](../windows/dialog-editor.md)합니다.  
  
### <a name="import"></a>가져오기
 열립니다는 **가져올** 대화 상자는 이동할 수 있습니다 리소스 수를 현재 프로젝트로 가져올 하려고 합니다. 비트맵, 아이콘, 커서, HTML 리소스 파일, 사운드(.WAV) 리소스 파일 또는 사용자 지정 리소스 파일을 가져올 수 있습니다.  
  
### <a name="custom"></a>사용자 지정
 열립니다는 [새 사용자 지정 리소스 대화 상자](../windows/new-custom-resource-dialog-box.md) 사용자 지정 리소스를 만들 수 있습니다. 사용자 지정 리소스는 바이너리 편집기에서만 편집할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [방법: 리소스 파일 만들기](../windows/how-to-create-a-resource.md)