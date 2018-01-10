---
title: "안내선에 컨트롤 맞추기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eed9acf533939d305e42478bb87307bc0a055d3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="aligning-controls-on-a-guide"></a>안내선에 컨트롤 맞추기
컨트롤의 크기 조정 핸들 컨트롤을 이동 하 고 (이전에 가이드에 맞춤 컨트롤이 없는 경우) 안내선 컨트롤에 맞춤 안내선에 맞춤 합니다. 안내선을 이동할 때 여기에 맞춘 컨트롤도 이동 합니다. 컨트롤 둘 이상의 안내선에 맞춤 안내선 중 하나를 이동할 때 크기가 조정 됩니다.  
  
 안내선과 컨트롤의 간격을 결정 하는 눈금자의 눈금 표시는 대화 상자 단위 (Dlu)로 정의 됩니다. DLU는 일반적으로 8 포인트 MS Shell Dlg 대화 상자 글꼴의 크기를 기반으로 합니다. 가로 DLU 대화 상자 글꼴 4로 나눈 값의 평균 너비입니다. 세로 DLU 평균 8로 나눈 글꼴 높이 같습니다.  
  
### <a name="to-size-a-group-of-controls-with-guides"></a>가이드로 컨트롤 그룹의 크기를 조정 하려면  
  
1.  안내선에 컨트롤 (또는 컨트롤)의 한 쪽을 맞춥니다.  
  
2.  컨트롤 (또는 컨트롤)의 다른 쪽에 대 한 지침을 끕니다.  
  
     여러 컨트롤에 필요한 경우 크기를 각각 두 번째 안내선에 맞춤을 합니다.  
  
3.  컨트롤 (또는 컨트롤) 크기를 조정 하거나 가이드를 이동 합니다.  
  
### <a name="to-change-the-intervals-of-the-tick-marks"></a>눈금 표시의 간격을 변경 하려면  
  
1.  **형식** 메뉴 선택 **가이드 설정**합니다.  
  
2.  에 [안내선 설정 대화 상자](../windows/guide-settings-dialog-box.md)에 **눈금 간격** 필드에서 Dlu의 새로운 너비 및 높이 지정 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 편집기 상태 (안내선과 모눈)](../windows/dialog-editor-states-guides-and-grids.md)   
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)

