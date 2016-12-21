---
title: "__vmx_vmwrite | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmwrite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmwrite 내장 함수"
  - "VMWRITE 명령"
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmwrite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 현재 가상 컴퓨터 제어 구조 \(VMCS\)에 지정 된 필드에 지정 된 값을 씁니다.  
  
## 구문  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] `Field`|쓰기 VMCS 필드입니다.|  
|\[in\] `FieldValue`|VMCS 필드에 쓸 값입니다.|  
  
## 반환 값  
 0  
 작업이 성공 했습니다.  
  
 1  
 작업 실패와 확장 된 상태에서 사용할 수 있는 `VM-instruction error field` 현재 VMCS의.  
  
 2  
 사용 가능한 상태가 없으면 작업이 실패 했습니다.  
  
## 설명  
 `__vmx_vmwrite` 함수는 해당 하는 `VMWRITE` 컴퓨터 명령.  값은 `Field` 매개 변수는 인텔 문서에 설명 되어 있는 인코딩된 필드 인덱스입니다.  검색 문서, "인텔 가상화 기술 사양에는 ia\-32 인텔 아키텍처"에 대 한 자세한 내용은 번호 C97063\-002에서를 문서는 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트, 및 다음 해당 문서의 부록 C를 참조 하십시오.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmread](../intrinsics/vmx-vmread.md)