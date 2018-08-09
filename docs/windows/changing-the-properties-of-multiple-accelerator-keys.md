---
title: 여러 액셀러레이터 키 속성 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac3cde3d986869f16431642d5c10632e2dbeefde
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642504"
---
# <a name="changing-the-properties-of-multiple-accelerator-keys"></a>여러 액셀러레이터 키 속성 변경
### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>여러 액셀러레이터 키 속성을 변경 하려면  
  
1.  액셀러레이터 키 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  액셀러레이터 키를 누른 채로 변경 하려면 선택 합니다 **Ctrl** 각각 클릭 하면 키입니다.  
  
3.  로 이동 합니다 [속성 창](/visualstudio/ide/reference/properties-window) 선택한 가속기 공유의 모든 값을 입력 합니다.  
  
    > [!NOTE]
    >  각 한정자 값이 부울 속성으로 표시 합니다 **속성** 창입니다. 변경 하는 경우는 [한정자](../windows/accelerator-modifier-property.md) 값을 **속성** 창 액셀러레이터 키 테이블에서 새 한정자 있었습니까 이전에 한정자에는 추가으로 처리 합니다. 이 인해 모든 한정자 값을 설정 하는 경우 해야 모든 액셀러레이터 키를 동일한 공유 하는지 확인 하려면 모든 설정 **한정자** 설정 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 테이블 편집](../windows/editing-accelerator-tables.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)