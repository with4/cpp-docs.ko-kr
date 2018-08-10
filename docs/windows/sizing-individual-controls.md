---
title: 개별 컨트롤 크기 조정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20dc5eb7af4195c9861d09761da245cdd5d3217d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652216"
---
# <a name="sizing-individual-controls"></a>각 컨트롤 크기 조정
컨트롤의 크기를 조정 하려면 크기 조정 핸들을 사용 합니다. 크기 조정 핸들의 포인터가 셰이프 컨트롤을 조정할 수 있는 방향을 가리키도록 변경 됩니다. 현재 크기 조정 핸들은 실선입니다. 크기 조정 핸들을 속이 빈 경우 컨트롤이 해당 축을 따라 크기 조정할 수 없습니다.  
  
 또한 가이드 또는 여백 컨트롤 스냅 하 여 컨트롤의 크기를 변경할 수 있습니다 또는 하나 이동 하 여 기본 컨트롤 및 다른에서 가이드입니다.  
  
### <a name="to-size-a-control"></a>컨트롤의 크기  
  
1.  컨트롤을 선택 합니다.  
  
2.  컨트롤의 크기를 변경 하려면 크기 조정 핸들을 끕니다.  
  
    -   위와 옆에 있는 크기 조정 핸들 가로 또는 세로 크기를 변경 합니다.  
  
    -   모퉁이에 크기 조정 핸들 가로 및 세로 크기를 변경합니다.  
  
    > [!TIP]
    >  누른 여 한 번에 하나의 대화 상자 단위 (DLU) 컨트롤을 조정할 수 있습니다는 **Shift** 키 및 사용 하 여는 **오른쪽 화살표** 하 고 **아래쪽 화살표** 키입니다.  
  
### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>자동으로 그 텍스트에 맞게 컨트롤의 크기  
  
1.  선택할 **콘텐츠 크기를 조정** 에서 합니다 **형식** 메뉴.  
  
 \- 또는 -  
  
-   선택한 컨트롤을 마우스 오른쪽 단추로 클릭 **콘텐츠 크기를 조정** 바로 가기 메뉴에서.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)