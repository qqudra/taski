# ������� ����� �� ������ �������� ����,
# ������� �������� ����� �� � ������������� Python 3.9.
FROM python:3.9

# ��������� � ������ � ���������� /app: � ��� ����� ������� ��� �������.
# ���� ���������� � ��������� ������ ���, ��� ����� �������. 
# �������� ���������� ����� ���� �����.
WORKDIR /app
# ���������� ���������� ����� ����������� � ���������� /app

# ����������� � ���������� ���������� ���� ������������
# � ������� ���������� (������� ���������� � ��� /app).
COPY requirements.txt .

# ��������� � ������� ���������� ������� ���������
# ��� ��������� ������������.
RUN pip install gunicorn==20.1.0
RUN pip install -r requirements.txt --no-cache-dir

# ����������� �� ����������� ���������� 
# ��� ���������� ���������� ����������, ��� �������� Dockerfile,
# � ������� ������� ���������� ������ � /app.
COPY . .

# ��� ������ ���������� ��������� ������ ����������.
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]