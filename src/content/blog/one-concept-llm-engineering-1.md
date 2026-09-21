---
title: "빈칸으로 이해하는 LLM 엔지니어링 (1)"
description: "앞에 주어진 말에 따라 달라지는 답을 빈칸 예시로 설명합니다. 프롬프트, 컨텍스트, 하네스가 무엇을 가리키는지 살펴봅니다."
pubDate: 2026-09-13
updatedDate: 2026-09-21
seriesOrder: 1
seriesLabel: "입력 · 앞말에 따라 달라지는 답"
---

빈칸을 하나 드리겠습니다.

“비 오는 날엔 따뜻한 ___.”

아마 머릿속에 “국물”이나 “커피” 같은 말이 자연스럽게 떠올랐을 겁니다. 앞에 있는 말들이 뒤에 올 말을 떠올리는 데 영향을 준 거죠.

대화형 AI에 질문을 입력하면 대규모 언어 모델, 즉 LLM으로 생성한 답을 받습니다. LLM은 학습 내용과 입력된 말을 바탕으로 다음 말을 차례로 선택합니다.

## 앞에 주어진 말에 따라 답이 달라집니다

두 문장에서 빈칸 앞부분만 바꿨습니다.

“한여름 땡볕에 걷다가, 시원한 ___.”
“한겨울 눈길을 걷다가, 따뜻한 ___.”

<figure>
  <img src="/images/series/seasons.webp" alt="여름 풍경 앞의 얼음물과 아이스커피, 겨울 창가의 따뜻한 차와 국물" width="1440" height="960" loading="lazy" />
  <figcaption>계절과 온도를 다르게 적으면 떠올리는 음료나 음식도 달라질 수 있습니다. 문장 예시를 설명하기 위해 생성한 삽화입니다.</figcaption>
</figure>

빈칸 앞에 적은 계절에 따라 떠오르는 말이 달라질 수 있습니다.

<figure>
  <picture>
    <source media="(max-width: 540px)" srcset="/images/series/01-same-blank-different-context-mobile.svg" width="360" height="456" />
    <img src="/images/series/01-same-blank-different-context.svg" alt="여름 문장에는 물이나 아이스커피, 겨울 문장에는 차나 국물을 떠올리는 예시" width="720" height="288" loading="lazy" />
  </picture>
  <figcaption>같은 빈칸이어도 앞에 적은 상황에 따라 떠올리는 답이 달라질 수 있습니다. 실제 AI 응답을 측정한 결과는 아닙니다.</figcaption>
</figure>

AI에 입력하는 질문이나 지시를 “프롬프트”라고 부릅니다. 프롬프트에 목적과 필요한 정보를 적으면 답이 달라질 수 있습니다. 바뀐 답이 더 나은지는 결과를 비교해야 합니다.

## 같은 질문의 다른 답, 틀린 사실, 이전 대화

같은 질문에도 다른 답이 나올 수 있습니다. 이어질 만한 말이 여럿이고, 그중 무엇을 고르는지는 모델과 설정에 따라 달라집니다. 이미 생성한 말도 그다음 말에 영향을 줍니다.

자연스러운 문장에도 틀린 사실이 들어갈 수 있습니다. “모르겠습니다”라는 답을 받을 때도 있지만 확신에 찬 문장에 틀린 사실이 들어갈 수도 있습니다. 사실 확인이 필요한 답은 자료와 대조해야 합니다.

대화 앱에서는 이전 대화나 저장해 둔 정보가 내가 방금 쓴 질문과 함께 전달되기도 합니다. 어떤 정보가 함께 전달되는지도 답에 영향을 줍니다.

## AI에 전달할 정보와 실행 절차

답이 마음에 들지 않으면 내가 쓴 질문과 함께 어떤 정보가 전달됐는지부터 확인할 수 있습니다. 질문을 다듬거나 필요한 자료를 더 준 뒤 바뀐 답을 비교합니다.

프롬프트 엔지니어링은 AI에 입력할 지시를 쓰고 다듬는 일입니다. 컨텍스트 엔지니어링에서는 지시뿐 아니라 대화 기록, 참고 자료, 도구로 가져온 정보까지 골라 필요한 때 전달합니다.

AI에 정보를 전달하고 도구를 실행하며 작업 상태와 결과를 확인하는 프로그램과 절차를 하네스라고 부릅니다. 예를 들어 AI로 파일을 고칠 때는 파일을 읽고 수정할 도구를 제공하며 수정한 결과를 검사하는 과정도 하네스에 포함됩니다.

<span id="다음-글부터"></span>

## 지시, 자료, 실행을 차례로 비교합니다

2화에서는 지시를 바꾼 실험을, 3화에서는 질문과 함께 전달한 자료를, 4화에서는 실행과 결과 확인을 다룹니다. 각 글에는 실제로 비교한 조건과 결과, 확인하지 못한 부분을 함께 적었습니다.

[2화: 프롬프트로 이동하기](/blog/one-concept-llm-engineering-2/)

## 참고 자료

- [불확실성을 인정하는 답변과 사실 확인](https://platform.claude.com/docs/en/test-and-evaluate/strengthen-guardrails/reduce-hallucinations)
- [이전 대화를 입력으로 전달하는 방법](https://platform.claude.com/docs/en/build-with-claude/working-with-messages)
- [컨텍스트 엔지니어링에서 다루는 정보](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- [도구 실행과 결과 검사를 포함한 하네스 사례](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
