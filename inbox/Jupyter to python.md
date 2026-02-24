Add this to jupyter cell at end
!jupyter nbconvert --to script your_notebook_name.ipynb

Step 1: Add the Tag in the Web GUI
​Open your notebook in the Jupyter Web GUI.
​Select the cell you want to exclude.
​In the right-hand sidebar, click on the Property Inspector (the icon looks like a gear or two overlapping squares).
​Find the Add Tag box and type ignore (or skip), then press Enter.


!jupyter nbconvert --to script your_notebook.ipynb --TagRemovePreprocessor.remove_cell_tags="['ignore']"


- **Scalable:** You can use multiple tags (e.g., ignore, test_data, temp).
