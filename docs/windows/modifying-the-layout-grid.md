---
title: 레이아웃 모눈 수정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
ms.assetid: ec31f595-7542-485b-806f-efbaeccc1b3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bafa66a382566ed096f70c752c461d8f3e2ca85
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010291"
---
# <a name="modifying-the-layout-grid"></a>레이아웃 모눈 수정
배치 하거나 대화 상자에서 컨트롤 정렬 하는 경우에 보다 정확한 위치에 대 한 레이아웃 모눈을 사용할 수 있습니다. 표에서 켜져 컨트롤 "에 맞출" 그리드의 점선은 자석 처럼 나타납니다. 이 "눈금에 맞춤" 기능을 켜고 끄는 하 고 레이아웃 표 형태 셀의 크기를 변경할 수 있습니다.  
  
### <a name="to-turn-the-layout-grid-on-or-off"></a>레이아웃 모눈 켜기 / 끄기를  
  
1.  **형식** 메뉴 선택 **안내선 설정**합니다.  
  
2.  에 [안내선 설정 대화 상자](../windows/guide-settings-dialog-box.md)을 선택 하거나 선택을 취소 합니다 **그리드** 단추.  
  
     개별 메서드는 눈금을 제어할 수 있습니다 **대화 상자** 사용 하 여 편집기 창을 **눈금 설정/해제** 단추를 [대화 상자 편집기 도구 모음](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)합니다.  
  
### <a name="to-change-the-size-of-the-layout-grid"></a>레이아웃 모눈의 크기를 변경 하려면  
  
1.  **형식** 메뉴 선택 **안내선 설정**합니다.  
  
2.  에 [안내선 설정 대화 상자](../windows/guide-settings-dialog-box.md)을 표의 셀에 대 한 Dlu 높이 너비를 입력 합니다. 최소 높이 또는 너비는 4 개의 Dlu입니다. Dlu에 대 한 자세한 내용은 참조 하세요. [대화 상자에서 컨트롤의 배치](../windows/arrangement-of-controls-on-dialog-boxes.md)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 편집기 상태 (안내선과 모눈)](../windows/dialog-editor-states-guides-and-grids.md)   
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)