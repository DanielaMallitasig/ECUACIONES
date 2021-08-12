# Collapsing clm factors works

    Code
      extract_eq(model_logit)
    Output
      $$
      \begin{aligned}
      \log\left[ \frac { P( \operatorname{A} \geq \operatorname{B} ) }{ 1 - P( \operatorname{A} \geq \operatorname{B} ) } \right] &= \alpha_{1} + \beta_{1}(\operatorname{categorical}_{\operatorname{b}}) + \beta_{2}(\operatorname{categorical}_{\operatorname{c}}) + \beta_{3}(\operatorname{categorical}_{\operatorname{d}}) + \beta_{4}(\operatorname{categorical}_{\operatorname{e}}) + \beta_{5}(\operatorname{continuous}) + \beta_{6}(\operatorname{categorical}_{\operatorname{b}} \times \operatorname{continuous}) + \beta_{7}(\operatorname{categorical}_{\operatorname{c}} \times \operatorname{continuous}) + \beta_{8}(\operatorname{categorical}_{\operatorname{d}} \times \operatorname{continuous}) + \beta_{9}(\operatorname{categorical}_{\operatorname{e}} \times \operatorname{continuous}) \\
      \log\left[ \frac { P( \operatorname{B} \geq \operatorname{C} ) }{ 1 - P( \operatorname{B} \geq \operatorname{C} ) } \right] &= \alpha_{2} + \beta_{1}(\operatorname{categorical}_{\operatorname{b}}) + \beta_{2}(\operatorname{categorical}_{\operatorname{c}}) + \beta_{3}(\operatorname{categorical}_{\operatorname{d}}) + \beta_{4}(\operatorname{categorical}_{\operatorname{e}}) + \beta_{5}(\operatorname{continuous}) + \beta_{6}(\operatorname{categorical}_{\operatorname{b}} \times \operatorname{continuous}) + \beta_{7}(\operatorname{categorical}_{\operatorname{c}} \times \operatorname{continuous}) + \beta_{8}(\operatorname{categorical}_{\operatorname{d}} \times \operatorname{continuous}) + \beta_{9}(\operatorname{categorical}_{\operatorname{e}} \times \operatorname{continuous})
      \end{aligned}
      $$

---

    Code
      extract_eq(model_probit)
    Output
      $$
      \begin{aligned}
      P( \operatorname{A} \geq \operatorname{B} ) &= \Phi[\alpha_{1} + \beta_{1}(\operatorname{categorical}_{\operatorname{b}}) + \beta_{2}(\operatorname{categorical}_{\operatorname{c}}) + \beta_{3}(\operatorname{categorical}_{\operatorname{d}}) + \beta_{4}(\operatorname{categorical}_{\operatorname{e}}) + \beta_{5}(\operatorname{continuous}) + \beta_{6}(\operatorname{categorical}_{\operatorname{b}} \times \operatorname{continuous}) + \beta_{7}(\operatorname{categorical}_{\operatorname{c}} \times \operatorname{continuous}) + \beta_{8}(\operatorname{categorical}_{\operatorname{d}} \times \operatorname{continuous}) + \beta_{9}(\operatorname{categorical}_{\operatorname{e}} \times \operatorname{continuous})] \\
      P( \operatorname{B} \geq \operatorname{C} ) &= \Phi[\alpha_{2} + \beta_{1}(\operatorname{categorical}_{\operatorname{b}}) + \beta_{2}(\operatorname{categorical}_{\operatorname{c}}) + \beta_{3}(\operatorname{categorical}_{\operatorname{d}}) + \beta_{4}(\operatorname{categorical}_{\operatorname{e}}) + \beta_{5}(\operatorname{continuous}) + \beta_{6}(\operatorname{categorical}_{\operatorname{b}} \times \operatorname{continuous}) + \beta_{7}(\operatorname{categorical}_{\operatorname{c}} \times \operatorname{continuous}) + \beta_{8}(\operatorname{categorical}_{\operatorname{d}} \times \operatorname{continuous}) + \beta_{9}(\operatorname{categorical}_{\operatorname{e}} \times \operatorname{continuous})]
      \end{aligned}
      $$

---

    Code
      extract_eq(model_logit, index_factors = TRUE)
    Output
      $$
      \log\left[ \frac { P( \operatorname{A} \geq \operatorname{B} ) }{ 1 - P( \operatorname{A} \geq \operatorname{B} ) } \right] = \alpha + \operatorname{categorical}_{\operatorname{i}} + \operatorname{continuous} + \left(\operatorname{categorical}_{\operatorname{i}} \times \operatorname{continuous}\right) \\
      \log\left[ \frac { P( \operatorname{B} \geq \operatorname{C} ) }{ 1 - P( \operatorname{B} \geq \operatorname{C} ) } \right] = \alpha + \operatorname{categorical}_{\operatorname{i}} + \operatorname{continuous} + \left(\operatorname{categorical}_{\operatorname{i}} \times \operatorname{continuous}\right)
      $$

---

    Code
      extract_eq(model_probit, index_factors = TRUE)
    Output
      $$
      P( \operatorname{A} \geq \operatorname{B} ) = \Phi[\alpha + \operatorname{categorical}_{\operatorname{i}} + \operatorname{continuous} + \left(\operatorname{categorical}_{\operatorname{i}} \times \operatorname{continuous}\right)] \\
      P( \operatorname{B} \geq \operatorname{C} ) = \Phi[\alpha + \operatorname{categorical}_{\operatorname{i}} + \operatorname{continuous} + \left(\operatorname{categorical}_{\operatorname{i}} \times \operatorname{continuous}\right)]
      $$

# Ordered models with clm work

    $$
    \begin{aligned}
    \log\left[ \frac { P( \operatorname{A} \geq \operatorname{B} ) }{ 1 - P( \operatorname{A} \geq \operatorname{B} ) } \right] &= \alpha_{1} + \beta_{1}(\operatorname{continuous\_1}) + \beta_{2}(\operatorname{continuous\_2}) \\
    \log\left[ \frac { P( \operatorname{B} \geq \operatorname{C} ) }{ 1 - P( \operatorname{B} \geq \operatorname{C} ) } \right] &= \alpha_{2} + \beta_{1}(\operatorname{continuous\_1}) + \beta_{2}(\operatorname{continuous\_2})
    \end{aligned}
    $$

---

    $$
    \begin{aligned}
    \log\left[ \frac { P( \operatorname{A} \geq \operatorname{B} ) }{ 1 - P( \operatorname{A} \geq \operatorname{B} ) } \right] &= \alpha_{1} + \beta_{1}(\operatorname{continuous\_1})\ + \\
    &\quad \beta_{2}(\operatorname{continuous\_2}) \\
    \log\left[ \frac { P( \operatorname{B} \geq \operatorname{C} ) }{ 1 - P( \operatorname{B} \geq \operatorname{C} ) } \right] &= \alpha_{2} + \beta_{1}(\operatorname{continuous\_1})\ + \\
    &\quad \beta_{2}(\operatorname{continuous\_2})
    \end{aligned}
    $$

---

    $$
    \begin{aligned}
    P( \operatorname{A} \geq \operatorname{B} ) &= \Phi[\alpha_{1} + \beta_{1}(\operatorname{continuous\_1}) + \beta_{2}(\operatorname{continuous\_2})] \\
    P( \operatorname{B} \geq \operatorname{C} ) &= \Phi[\alpha_{2} + \beta_{1}(\operatorname{continuous\_1}) + \beta_{2}(\operatorname{continuous\_2})]
    \end{aligned}
    $$

---

    $$
    \begin{aligned}
    P( \operatorname{A} \geq \operatorname{B} ) &= \Phi[\alpha_{1} + \beta_{1}(\operatorname{continuous\_1})\ + \\
    &\qquad\ \beta_{2}(\operatorname{continuous\_2})] \\
    P( \operatorname{B} \geq \operatorname{C} ) &= \Phi[\alpha_{2} + \beta_{1}(\operatorname{continuous\_1})\ + \\
    &\qquad\ \beta_{2}(\operatorname{continuous\_2})]
    \end{aligned}
    $$

---

    $$
    \begin{aligned}
    \log\left[ \frac { P( \operatorname{A} \geq \operatorname{B} ) }{ 1 - P( \operatorname{A} \geq \operatorname{B} ) } \right] &= -0.81 + 0.03(\operatorname{continuous\_1}) - 0.03(\operatorname{continuous\_2}) \\
    \log\left[ \frac { P( \operatorname{B} \geq \operatorname{C} ) }{ 1 - P( \operatorname{B} \geq \operatorname{C} ) } \right] &= 0.59 + 0.03(\operatorname{continuous\_1}) - 0.03(\operatorname{continuous\_2})
    \end{aligned}
    $$
