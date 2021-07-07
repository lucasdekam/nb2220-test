# Problem set 3

## Problem 3.1

1.  (A) Reservoir fixes $p,T$, system conserves $N$, so $G(N,p,T)$
        (Gibbs free energy)

    (B)  Reservoir fixes $T$, system conserves $N,V$, so $F(N,V,T)$
        (Helmholtz free energy)

    (C) Reservoir fixes $\mu,T$, system conserves $V$, so
        $\Phi(\mu,V,T)$ (Grand potential)

    (D) Reservoir fixes $p$, system conserves $N,E,S$, so $H(N,p,E)$
        (Enthalpy)

2.  $$dE = TdS - pdV + \mu dN$$

    and

    $$F = E - TS$$

    so

    $$\begin{aligned}
            dF &= d(E-TS)\\
            &= dE - d(TS)\\
            &= dE - SdT - TdS\\
            &= (Tds - pdV + \mu dN) -SdT - TdS\\
            &= -SdT - pdV + \mu dN
    \end{aligned}$$

3.  $$\Phi(\mu,V,T)=F(N,V,T) - \frac{\partial F}{\partial N}N = F - \mu N$$

    $$d\Phi= -SdT -pdV - Nd\mu$$

4.  $$G(N,p,T) = F(N,V,T) - \frac{\partial F}{\partial V}V = F + pV$$

    The Gibbs free energy is used for isothermal-isobaric processes.

5.  Both $G$ and $N$ are extensive, and $p,T$ are intensive. Therefore

    $$G(\lambda N,p,T) = \lambda G(N,p,T)$$

    so, $G \propto N$, so $G$ can be written as

    $$G(N,p,T) = \mu(p,T) N$$

## Problem 3.2

1.  Extensive: $N,V,E,S$, intensive: $p,T,\mu,\rho$

2.  Isothermal processes. Systems in contact with a heat bath / thermal
    reservoir.

3.  $N,V,T$

4.  In an isothermal process, the amount of work corresponds to the
    change in free energy

    $$\begin{aligned}
            F_B - F_A &= - \int \limits_{V_A}^{V_B} p dV \\
            &= - \int \limits_{V_A}^{V_B} \frac{Nk_\mathrm{B}T}{V}dV\\
            &= Nk_\mathrm{B}T \ln{\frac{V_A}{V_B}}
    \end{aligned}$$

5.  This amount of energy corresponds to the amount of work performed on
    the gas during the isothermal process.

6.  There is no heat exchange $dQ=0$, so

    $$\begin{aligned}
            E_B - E_A &= - \int \limits_{V_A}^{V_B} p dV \\
            &= - \int \limits_{V_A}^{V_B} \frac{Nk_\mathrm{B}T}{V}dV\\
            &= Nk_\mathrm{B}T \ln{\frac{V_A}{V_B}}    
    \end{aligned}$$

    Same amount as in previous question, but the
    process is different.

7.  Did you not forget one of the subquestions? No.

## Problem 3.3

1.  If one can build a \"magic machine\" that can convert heat
    completely into work (violating Kelvin's law), then one can power a
    heat pump, to transport heat from a cold to a hot reservoir,
    {numref}`fig:second_law_non_Kelvin`. The combined effect of this
    magic machine plus heat pump is that heat is flowing from a cold
    reservoir to a hot reservoir, violating the law of Clausius. So,
    violating Kelvin's law implies violating Clausius's law.

    ```{figure} images/Second_law_non_Kelvin.png
    ---
    name: fig:second_law_non_Kelvin
    ---
    Magic machine, violating Kelvin's law, powering a heat pump. The
    combined effect of the machine plus heat pump is that energy is
    flowing from cold to hot without any external energy input,
    violating the law of
    Clausius.
    ```

2.  Heat can be converted into work, but not completely (according to
    Kelvin's law and practical experience). Some amount of heat has to
    be deposited elsewhere. If, however, one could build a magic heat
    pump (violating the law of Clausius) that transports heat from cold
    to hot, without any external input of work, one could pump the waste
    heat of the machine back in the hot reservoir for free, see
    {numref}`fig:second_law_non_Clausius`. The two devices combined
    would act like a machine converting heat completely into work. This
    would violate Kelvin's law. So, violating Clausius's law implies
    violating Kelvin's law. Combined with the previous answer, we see
    that the laws are identical.

    ```{figure} images/Second_law_non_Clausius.png
    ---
    name: fig:second_law_non_Clausius
    ---
    Magic heat pump, violating Clausius's law, pumping back the waste
    heat of a machine. The combined effect of both devices is a machine
    that converts heat completely into work, violating Kelvin's
    law.
    ```

## Problem 3.4

1.  See {numref}`fig:Carnot_cycle`.

    ```{figure} images/Carnot_cycle.png
    ---
    name: fig:Carnot_cycle
    ---
    The Carnot cycle in a $p,V$-diagram and a $T,S$-diagram. Adiabatic
    branches are BC and DA. Isothermal branches are AB
    and CD.
    ```

2.  This is not in conflict with the second law of thermodynamics,
    because not all heat is converted into work, but is also deposited
    elsewhere. The efficiency is not 1.

3.  The efficiency of the Carnot cycle is

    $$\eta = \frac{W}{Q_\mathrm{H}}=\frac{Q_\mathrm{H}-Q_\mathrm{C}}{Q_\mathrm{H}}=1-\frac{Q_\mathrm{C}}{Q_\mathrm{H}}.$$

    Using

    $$E = \frac{3}{2} N k_\mathrm{B}T$$

    one can see that $dE=0$
    along the isothermal branches, because $dT=0$, such that $dQ = pdV$
    and

    $$Q_\mathrm{H} = \int \limits_A^B \frac{Nk_\mathrm{B}T_\mathrm{H}}{V}dV = Nk_\mathrm{B}T_\mathrm{H}\ln{\frac{V_B}{V_A}}$$

    and

    $$  
        Q_\mathrm{C} = Nk_\mathrm{B}T_\mathrm{C} \ln{\frac{V_D}{V_C}}
    $$

    Along the adiabatic branches $dQ=0$, such that

    $$dE = \frac{3}{2}Nk_\mathrm{B} dT = - pdV = \frac{Nk_\mathrm{B}T}{V}dV$$

    leading to

    $$\begin{aligned}
            \frac{dT}{T} = \frac{2}{3}\frac{dV}{V},
    \end{aligned}$$

    so

    $$TV^{\frac{2}{3}} = \mathrm{constant}$$

    meaning

    $$\begin{aligned}
            T_H V_B^{\frac{2}{3}} &= T_C V_C^{\frac{2}{3}}\\
            T_C V_D^{\frac{2}{3}} &= T_H V_A^{\frac{2}{3}}
    \end{aligned}$$

    so

    $$\frac{V_B}{V_A} = \frac{V_C}{V_D}$$

    This equation shows that if one takes the ratio of the heats, the
    logarithms will cancel, and

    $$\eta = 1 - \frac{Q_\mathrm{C}}{Q_\mathrm{H}} = 1 - \frac{T_\mathrm{C}}{T_\mathrm{H}}$$

## Problem 3.5

1.  Using the previous exercise and

    $$\eta = 1 - \frac{Q_\mathrm{C}}{Q_\mathrm{H}} = 1 - \frac{T_\mathrm{C}}{T_\mathrm{H}}$$

    one can show quickly that

    $$\frac{Q_\mathrm{H}}{T_\mathrm{H}} - \frac{Q_\mathrm{C}}{T_\mathrm{C}}=0.$$

2.  If both machines perform the same amount of work
    $W=Q_\mathrm{H}-Q_\mathrm{C}=Q'_\mathrm{H}-Q'_\mathrm{C}$ and using
    that $\eta \leq \eta_\mathrm{Carnot}$ to derive that
    $Q_\mathrm{H}<Q'_\mathrm{H}$, one can show that

    $$\begin{aligned}
        \frac{Q'_\mathrm{H}}{T_\mathrm{H}} - \frac{Q'_\mathrm{C}}{T_\mathrm{C}} &= \frac{Q'_\mathrm{H}-Q_\mathrm{H}+Q_\mathrm{H}}{T_\mathrm{H}} - \frac{Q_\mathrm{C}+Q'_\mathrm{H}-Q_\mathrm{H}}{T_\mathrm{C}} \\
        &=\frac{Q_\mathrm{H}}{T_\mathrm{H}} - \frac{Q_\mathrm{C}}{T_\mathrm{C}} + (Q'_\mathrm{H}-Q_\mathrm{H})\left(\frac{1}{T_\mathrm{H}} - \frac{1}{T_\mathrm{C}} \right)\\
        &= (Q'_\mathrm{H}-Q_\mathrm{H})\left(\frac{1}{T_\mathrm{H}} - \frac{1}{T_\mathrm{C}} \right) \leq 0
    \end{aligned}$$

    With some more math one can derive now that for *any* cycle

    $$\oint \frac{dQ}{T} \leq 0.$$

    This is called the Clausius
    inequality. A consequence is that for an adiabatic process
    $S_2\geq S_1$ if the system undergoes a change from state 1 to
    state 2.

    > The entropy of an isolated system never decreases.

    This statement follows directly from Boltzmann's definition of
    entropy. His definition also implies the laws of thermodynamics, but
    for that one needs to introduce a microscopic world. That will be
    the topic of the next session.
