---
title: 안내선에 컨트롤 맞추기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLUs (dialog units)
- controls [C++], aligning
- Dialog editor, snap to guides
- guides, tick mark interval
- dialog box controls, placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a1a586a3a17e829d883dff96c12f6a2fdabe669f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643860"
---
# <a name="aligning-controls-on-a-guide"></a>안내선에 컨트롤 맞추기
컨트롤의 크기 조정 핸들 컨트롤을 이동 하 고 (이전에 가이드에 맞춰진 컨트롤이 있는 경우) 가이드 컨트롤 맞춤 안내선에 맞춤 합니다. 가이드 이동 될 때 컨트롤에 모눈을 이동 합니다. 둘 이상의 가이드에 맞춰진 컨트롤 가이드 중 하나를 이동 하면 크기가 조정 됩니다.  
  
 안내선과 컨트롤의 간격을 결정 하는 눈금자의 눈금은 대화 상자 단위 (Dlu)로 정의 됩니다. DLU는 일반적으로 8 포인트 MS Shell Dlg 대화 상자 글꼴 크기를 기반으로 합니다. 가로 DLU는 4로 나눈 대화 상자 글꼴의 평균 너비입니다. 세로 DLU은 평균 8로 나눈 글꼴 높이입니다.  
  
### <a name="to-size-a-group-of-controls-with-guides"></a>그룹 가이드를 사용 하 여 컨트롤의 크기  
  
1.  안내선에 컨트롤 (또는 컨트롤)의 한 쪽을 맞춥니다.  
  
2.  컨트롤 (또는 컨트롤)의 다른 쪽에 대 한 지침을 끕니다.  
  
     여러 컨트롤을 사용 하 여 필요한 경우에 두 번째 가이드는 각 크기입니다.  
  
3.  컨트롤의 크기는 (또는 컨트롤) 가이드 중 하나를 이동 합니다.  
  
### <a name="to-change-the-intervals-of-the-tick-marks"></a>눈금 표시의 간격을 변경 하려면  
  
1.  **형식** 메뉴 선택 **안내선 설정**합니다.  
  
2.  에 [안내선 설정 대화 상자](../windows/guide-settings-dialog-box.md)를 **모눈 간격** 필드 Dlu의 새 너비와 높이 지정 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 편집기 상태 (안내선과 모눈)](../windows/dialog-editor-states-guides-and-grids.md)   
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)