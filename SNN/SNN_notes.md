| Neuron | dynamics |      |
| ------ | ---- | ---- |
| LIF    | $ \tau_m \frac{dV}{dt} = - V + RI(t) $ |      |
| HH | $ C \frac {dV} {dt} = -(I_{Na} + I_{K} + I_{leak}) + I(t) $<br /><br />$\frac {dx} {dt} = \alpha_x (1-x)  - \beta_x$<br /><br /> | $ I_x = g_x (V - E_x) , \quad x\in \{Na, K, leak \} $<br /><br />$ g_{Na} = \bar{g}_{Na} m^3 h,   \qquad  m, h \in [ 0, 1 ]$<br />$ g_K = \bar{g}_K n^4,   \qquad  n \in [ 0, 1 ] $ |
| Izhikevich | $\frac{d V}{d t}=0.04 V^{2}+5 V+140-u+I$<br /><br />$\frac{d u}{d t}=a(b V-u)$ |      |



| Synapse  |      |      |
| -------- | ---- | ---- |
| AMPA1 | $I_{syn}=\bar{g}_{syn} s (V-E_{syn})$<br /><br />$\frac{d s}{d t}=-\frac{s}{\tau_{decay}}+\sum_{k} \delta(t-t_{j}^{k})$ |      |
| AMPA2 | $ I_{syn}=\bar{g}_{syn} s (V-E_{syn}) $ <br /><br /> $ \frac{ds}{dt} =\alpha[T](1-s)-\beta s $ |      |
| GABA$_a$ | $ I_{syn} = \bar{g}_{syn} s (V-E_{syn}) $<br /><br />$\frac{d s}{d t}=-\frac{s}{\tau_{decay}}+\sum_{k} \delta(t-t_{j}^{k})$ |  |
| NMDA     | $I_{syn}=\bar{g}_{syn} s (V-E_{syn})$<br /><br />$g(t) =\bar{g} \cdot (V-E_{syn}) \cdot g_{\infty} \cdot \sum_j s_j(t) $<br /><br />$g_{\infty}(V,[{Mg}^{2+}]_{o}) =(1+{e}^{-\alpha V} [{Mg}^{2+}]_{o}/\beta)^{-1} $<br /><br />$\frac{d s_{j}(t)}{dt} =-\frac{s_{j}(t)}{\tau_{decay}}+a x_{j}(t)(1-s_{j}(t))  $<br /><br />$\frac{d x_{j}(t)}{dt} =-\frac{x_{j}(t)}{\tau_{rise}}+ \sum_{k} \delta(t-t_{j}^{k}) $ |      |
| GABA$_{b1}$ | $\frac{d[R]}{dt} = k_3 [T](1-[R])- k_4 [R]$<br /><br />$ \frac{d[G]}{dt} = k_1 [R]- k_2 [G] $<br /><br />$ I_{GABA_{B}} =\overline{g}_{GABA_{B}} (\frac{[G]^{4}} {[G]^{4}+100}) (V-E_{GABA_{B}}) $ | |
| GABA$_{b2}$ | $\frac{d[D]}{dt}=K_{4}[R]-K_{3}[D]$<br /><br /> $\frac{d[R]}{dt}=K_{1}[T](1-[R]-[D])-K_{2}[R]+K_{3}[D]$<br /><br /> $\frac{d[G]}{dt}=K_{5}[R]-K_{6}[G]$<br /><br /> $I_{GABA_{B}}=\bar{g}_{GABA_{B}} \frac{[G]^{n}}{[G]^{n}+K_{d}}(V-E_{GABA_{B}})$ | |
| STP | $\frac{du}{dt} = -\frac{u}{\tau_f}+U(1-u^-)\delta(t-t_{spike})$ <br/><br /> $ \frac{dx}{dt} = \frac{1-x}{\tau_d}-u^+x^-\delta(t-t_{spike})$ | |
|  |  | |







| Learning Rules  |      |      |
| -------- | ---- | ---- |
| STDP     | $\Delta w_j = \sum\limits_{f=1}^N \sum\limits_{n=1}^N W(t_i^n - t_j^f) $<br />where<br />$W(x) = \begin{cases} A_+ \rm{exp} (-\frac x {\tau_+}), \quad x > 0 \\ -A_- \rm{exp} (\frac x {\tau_-}), \quad x < 0 \end{cases} $ |  |


| Networks     | dynamics | parameters |
| -------- | ---- | ---- |
| EI balanced | $ \tau \frac {dV_i}{dt} = -(V_i - V_{rest}) + I_i^{ext} + I_i^{net} (t) $<br /><br />where<br />$ I_i^{net} (t) = J_E \sum_\limits{j=1}^{pN_e} \sum\limits_{t_j^\alpha < t} f(t-t_j^\alpha ) - J_I \sum\limits_{j=1}^{pN_i} \sum\limits_{t_j^\alpha < t} f(t-t_j^\alpha )$<br /><br />where   $ f(t) = \begin{cases} {\rm exp} (-\frac t {\tau_s} ), \quad t \geq 0 \\0, \quad t < 0 \end{cases} $ | $ J_E = \frac 1 {\sqrt {pN_e}}, J_I = \frac 1 {\sqrt {pN_i}} $ |

