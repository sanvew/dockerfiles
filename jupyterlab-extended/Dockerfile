FROM jupyter/scipy-notebook

RUN conda update --all && \
    conda install --yes \
    plotly ipywidgets \
    jupyterlab-git \
    xeus-python \
    jupyterlab-lsp python-lsp-server && \
    conda clean --all -f -y && \
    jupyter labextension install nbdime-jupyterlab --no-build && \
    jupyter labextension install @jupyterlab/git --no-build && \
    jupyter labextension install @jupyterlab/latex --no-build && \
    jupyter labextension install @axlair/jupyterlab_vim --no-build && \
    jupyter labextension install @krassowski/jupyterlab-lsp --no-build && \
    jupyter lab build --dev-build=False --minimize=False && \
    jupyter lab clean && \
    jlpm cache clean && \
    npm cache clean --force && \
    rm -rf $HOME/.node-gyp && \
    rm -rf $HOME/.local && \
    fix-permissions $CONDA_DIR $HOME
